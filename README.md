🏠 Roomie
�
Find the right room. Find the right people. 

�
A modern Android roommate marketplace built with Kotlin and Jetpack Compose. 

�
￼ ￼ ￼ ￼ ￼ ￼ 

📱 Overview
Roomie is an Android roommate marketplace designed to connect people who have an available room with people looking for a place to live.
Unlike a traditional room-rental classifieds app, Roomie is designed around both sides of the roommate search:
🏠 People can list rooms available in their home.
🔎 People can post In Search Of (ISO) listings describing the room they need.
🤝 Users can discover potential roommate matches based on budget, location, move-in date, and lifestyle preferences.
💬 Users can communicate through in-app messaging.
❤️ Users can save rooms and potential roommates.
🛡️ Safety tools help users report and block suspicious listings or accounts.
🚧 Project status: Roomie is currently in development. The feature list describes the planned MVP and product direction.
🖼️ App Mockup
�
￼ 

The mockup illustrates the intended visual direction for the initial Roomie experience.
✨ Features
🏠 Find a Room
Browse available rooms with:
Monthly rent
Security deposit
Location
Move-in date
Furnished status
Private/shared bathroom
Parking
Utilities
Internet
Pets
Smoking
Lease length
House rules
Room photos
🔎 Search & Filters
Search by:
City
State
Neighborhood
ZIP code
Price range
Move-in date
Lease length
Additional filters:
Furnished
Private bathroom
Pets allowed
Smoking allowed
Parking
Utilities included
Internet included
Sort by:
Recommended
Price: low to high
Price: high to low
Newest
Distance
👥 In Search Of (ISO)
Users looking for housing can create an ISO listing containing:
Desired location
Maximum rent
Move-in date
Lease length
Furnished preference
Pets
Smoking
Lifestyle preferences
About me
🤝 Roommate Matching
Roomie can compare potential matches using factors such as:
Budget
Location
Move-in date
Pets
Smoking
Furnished preference
Lease length
Cleanliness
Sleep schedule
Social preferences
Guests
Lifestyle
Example:
94% Compatible

✓ Budget
✓ Location
✓ Move-in date
✓ No smoking
✓ No pets

Lifestyle Match: 91%
The score is a recommendation, not a guarantee of compatibility.
💬 Messaging
Users can:
Start conversations
Send messages
See timestamps
See unread messages
Reference a room listing
Block users
Report users
❤️ Saved Listings
Save:
Rooms
ISO listings
Potential roommates
🗺️ Map View
Browse rooms geographically using approximate listing locations.
Exact residential addresses should not be publicly exposed.
🔔 Notifications
Planned notifications include:
New messages
New matching rooms
Saved-search matches
Listing updates
New contacts
🛡️ Safety
Planned safety tools include:
Email verification
Optional phone verification
Verified profiles
Report listing
Report user
Block user
Scam warnings
Approximate location display
🧰 Tech Stack
Technology
Purpose
Kotlin
Application language
Jetpack Compose
Android UI
Material 3
Design system
MVVM
Application architecture
StateFlow
Reactive UI state
Coroutines
Asynchronous operations
Navigation Compose
Screen navigation
Firebase Authentication
User authentication
Cloud Firestore
Application database
Firebase Storage
Photos and media
Firebase Cloud Messaging
Notifications
Coil
Image loading
🏗️ Architecture
Roomie follows a clean MVVM-style architecture:
┌─────────────────────────┐
│       Jetpack Compose   │
│            UI           │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│        ViewModel        │
│   State + UI Logic      │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│       Repository        │
│     Data Operations     │
└────────────┬────────────┘
             │
             ▼
┌─────────────────────────┐
│         Firebase        │
│ Auth / Firestore /      │
│ Storage / Messaging     │
└─────────────────────────┘
UI components should not directly perform Firebase operations.
📂 Project Structure
Roomie/
├── app/
│   └── src/
│       └── main/
│           ├── java/com/example/roomie/
│           │   ├── data/
│           │   │   ├── firebase/
│           │   │   ├── model/
│           │   │   └── repository/
│           │   │
│           │   ├── navigation/
│           │   │
│           │   ├── ui/
│           │   │   ├── auth/
│           │   │   ├── home/
│           │   │   ├── search/
│           │   │   ├── map/
│           │   │   ├── listings/
│           │   │   ├── iso/
│           │   │   ├── messages/
│           │   │   ├── saved/
│           │   │   ├── profile/
│           │   │   └── settings/
│           │   │
│           │   ├── util/
│           │   └── MainActivity.kt
│           │
│           └── res/
│
├── docs/
│   └── images/
│       └── roomie-app-mockup.png
│
├── README.md
└── .gitignore
🗃️ Data Model
User
User
├── id
├── name
├── email
├── profilePhotoUrl
├── bio
├── city
├── state
├── verified
└── createdAt
RoomListing
RoomListing
├── id
├── ownerId
├── title
├── description
├── monthlyRent
├── securityDeposit
├── city
├── state
├── neighborhood
├── availableDate
├── furnished
├── privateBathroom
├── petsAllowed
├── smokingAllowed
├── parking
├── utilitiesIncluded
├── internetIncluded
├── leaseLength
├── currentRoommates
├── photos
└── createdAt
IsoListing
IsoListing
├── id
├── userId
├── title
├── description
├── desiredCity
├── desiredState
├── desiredNeighborhood
├── maximumRent
├── moveInDate
├── pets
├── smoking
├── furnishedPreference
├── leaseLength
├── lifestylePreferences
└── createdAt
☁️ Firebase Structure
Planned Firestore collections:
users/
  userId/

roomListings/
  listingId/

isoListings/
  listingId/

conversations/
  conversationId/

messages/
  messageId/

savedListings/
  savedListingId/
Firebase Authentication handles passwords and authentication. Passwords should never be stored manually in Firestore.
🚀 Setup
1. Requirements
Install:
Android Studio
Android SDK
JDK compatible with the project's Gradle/Android Gradle Plugin versions
A Firebase account
2. Clone the repository
git clone https://github.com/YOUR_USERNAME/Roomie.git
cd Roomie
Replace YOUR_USERNAME/Roomie with the actual repository.
3. Open in Android Studio
Open the project directory in Android Studio and allow Gradle to sync.
4. Create a Firebase project
Create a Firebase project and add an Android application using:
com.example.roomie
Enable:
Authentication
Cloud Firestore
Storage
Cloud Messaging
5. Add Firebase configuration
Download your Firebase Android configuration file:
google-services.json
Place it here:
app/google-services.json
Do not commit secrets or private credentials to a public repository.
6. Build
./gradlew assembleDebug
7. Run tests
./gradlew test
For connected Android tests:
./gradlew connectedAndroidTest
8. Run the app
Use Android Studio to launch Roomie on:
Android Emulator
Physical Android device
🔐 Firebase Security
Firestore security rules should enforce ownership and authorization.
At minimum:
Users can edit only their own profiles.
Users can edit/delete only their own listings.
Conversation messages are accessible only to participants.
Saved listings belong to the authenticated user.
Administrative actions require administrator authorization.
Never put Firebase Admin SDK credentials in the Android application.
🧭 Main Navigation
Welcome
   │
   ▼
Authentication
   │
   ▼
Home
 ┌─┼───────────┬───────────┐
 ▼ ▼           ▼           ▼
Search       Messages     Saved
 │              │
 ▼              ▼
Room Details   Chat
 │
 ├── Message
 └── Save

Home
 │
 ├── Find a Room
 │      └── Room Search
 │             └── Room Details
 │
 └── Find a Roommate
        └── ISO Search
               └── ISO Details

Profile
 ├── My Room Listings
 ├── My ISO Listings
 ├── Edit Profile
 └── Settings
🛣️ Roadmap
Phase 1 — Foundation
Android project
Kotlin
Jetpack Compose
Material 3
Firebase
Navigation
MVVM structure
Phase 2 — Authentication
Registration
Login
Logout
Password reset
Email verification
Google sign-in
Phase 3 — Profiles
Profile creation
Profile photo
About me
Location
Preferences
Profile editing
Phase 4 — Marketplace
Create room listing
Upload room photos
Edit listing
Delete listing
Search rooms
Filters
Sorting
Room details
Phase 5 — ISO
Create ISO
Edit ISO
Delete ISO
Browse ISO listings
ISO details
Phase 6 — Communication
Favorites
Messaging
Notifications
Blocking
Reporting
Phase 7 — Matching
Compatibility questionnaire
Matching algorithm
Match percentage
Recommended roommates
Phase 8 — Safety
Verified profiles
Scam detection
Safety center
Report review system
Future
Background checks
Identity verification
Digital lease signing
Rent/deposit payments
Video calls
Property-manager accounts
AI listing assistance
Commute-time calculations
Roommate reviews
🧪 Testing
Roomie should be tested for:
Authentication
Registration
Login
Logout
Profile editing
Room creation
Room editing
Room deletion
Search
Filtering
Favorites
ISO creation
Messaging
Notifications
Reporting
Blocking
Compatibility
Also test:
No internet
Slow internet
Firebase errors
Empty search results
Invalid forms
Failed image uploads
Deleted listings
Unauthorized access
🛡️ Privacy & Safety
Roomie is intended to be a marketplace for user-generated housing information.
Before public release, review applicable requirements involving:
Fair housing
Anti-discrimination
Privacy
User-generated content
Data protection
Rental regulations
Background checks
Payments
Security deposits
Terms of service
Community guidelines
Exact residential addresses should not be publicly exposed by default.
Users should be encouraged to meet potential roommates in a safe public location before sharing sensitive information.
🤝 Contributing
Contributions are welcome once the project is ready for external contributors.
Suggested workflow:
git checkout -b feature/your-feature
Make your changes, test them, then:
git add .
git commit -m "Add your feature"
git push origin feature/your-feature
Open a pull request on GitHub.
📄 License
The project license should be selected before public distribution.
Example:
Copyright © 2026 Roomie
All rights reserved.
📌 Project Status
🚧 In Development
The initial goal is a functional MVP containing:
✓ User accounts
✓ Profiles
✓ Room listings
✓ Room search
✓ Filters
✓ Room details
✓ ISO listings
✓ Saved listings
✓ Messaging
✓ Report/block tools
❤️ Vision
Roomie is designed to turn:
"I need a room."
and
"I have a room."
into:
"Here's someone who might be a great fit."
Find the right room. Find the right people.
⭐ If You Like Roomie
Star the repository, follow the project, and contribute ideas as the application develops.