# Quick-Ride User Manual

## Technical Requirements

To use SEP-Drive smoothly, your system should meet the following minimum requirements:

### 1. Hardware
- **RAM**: 2 GB (Recommended: 4 GB for smooth usage)
- **Processor**: Dual-Core (2.5 GHz or faster)
- **Storage**: 1 GB available for data and temporary storage

### 2. Software
#### Backend
- Java 17 or higher
- Maven 3.8+ (to build the project)
- Docker (for containerization)
- Docker Compose (to orchestrate frontend, backend, and database)

#### Frontend
- Node.js (v16 or higher)
- npm (Node Package Manager)

---

## Installation Guide

### 1. Prerequisites
- Ensure **Docker** and **Docker Compose** are installed:
  - Docker: [Download here](https://www.docker.com/products/docker-desktop)
  - Docker Compose: Already included in Docker Desktop

### 2. Download the Project
- Download the sep-drive-all-x86.tar and docker-compose.yml files.

### 3. Build Docker Containers
1. Open a terminal and navigate to the downloaded folder.
2. Load the images:
   ```bash
   docker load -i sep-drive-all-x86.tar
   ```
3. Wait until you see:
   ```
   Loaded image: sep-drive-backend:latest
   Loaded image: sep-drive-frontend:latest
   ```
4. Start the containers:
   ```bash
   docker-compose up
   ```
5. Wait until **both frontend and backend** are running.  
   _Running only one of them may cause errors._

### 4. Start the Application
- The application will run at:
  - **Frontend**: [http://localhost:4200](http://localhost:4200)
  - **Backend**: [http://localhost:8080](http://localhost:8080)
- Recommended: Use browser in **Incognito mode**.

### 5. Using the Application
- Open [http://localhost:4200](http://localhost:4200)
- You can register, log in, and create rides.

---

## User Guide

### 1. Registration
- Click **"Login"** on the navigation bar.
- In the login window, click **"Register here"**.
- Fill in required fields:
  - Username, First Name, Last Name, Email, Date of Birth, Password
- Select your role:
  - Customer or Driver
- (Optional) Upload a `.jpeg` profile picture.
- Click **"Register"**.

### 2. Login
- Click **"Login"** on the navigation bar.
- Enter username and password.
- A verification code will be sent via email.
- Enter the code and log in.
  - **Test Super-Code**: `super1`

### 3. Profile Management
- Click your username in the navigation bar.
- View:
  - First Name, Last Name, Role, Ratings, Number of Rides
  - (Drivers) Car Class

### 4. Requesting a Ride (Customer)
#### Creating a Request
1. Click **"Request Ride"**.
2. Enter start, destination, and optional stopovers:
   - via location search OR
   - via coordinates
3. Select vehicle type:
   - Small, Medium, Large
4. Click **"Submit Request"**.
5. Wait for driver offers.

#### Accepting an Offer
- Notification appears at bottom of page.
- Click **"View Offer"** for details.
- Click **"Accept Offer"** to start ride simulation.

### 5. Offering a Ride (Driver)
#### Sending an Offer
1. Click **"View Requests"**.
2. Enter your position.
3. View and sort available requests.
4. Select a request and click **"Send Offer"**.

#### Response to Offers
- If rejected: Notification appears at bottom of page.
- If accepted: Driver is redirected to ride simulation.

### 6. Ride Simulation
- Click **"Active Simulation"**.
- Map shows route with start, destination, and stopovers.
- Controls:
  - **Start** – begin simulation
  - **Resume** – continue paused simulation
  - **Pause** – pause simulation
  - **Simulation Duration** – adjust simulation speed
- Both customer and driver see simulation in real time.

### 7. Changing Route During Simulation (Customer Only)
- Pause the simulation to make changes.
- **Add a Stop**:
  - Use **"Add a new Stopover before: [Location]"**
  - Choose the position in the route with the slider.
- **Remove a Stop**:
  - Click **"Remove Stopover"** under unvisited locations.
- Changes automatically update the map, price, distance, and duration.

**Ending the Simulation**:
1. Click **"Complete"** when:
   - Destination is reached, OR  
   - Remaining stops/destination are removed and current location becomes endpoint.
2. Ensure sufficient wallet balance before completing.

**Notes**:
- If destination is reached but **"Please reach your Drop off..."** still shows, refresh the page.
- If rating fails to complete the simulation, refresh and change the endpoint.
- Do not remove pickup location even if it appears removable.

### 8. Ride Rating
- After completion, a popup **"Rate your Driver/Customer"** appears.
- Give a rating and click **"Submit"**.
- Rating is saved and linked to the ride.

### 9. Chat
**Conditions**:
- Customer has made a request.
- Driver has sent an offer.
- Offer is not yet accepted or rejected.

**Usage**:
- **"Chat"** button appears for both customer and driver.
- Click to open chat window.
- Exchange messages until offer is accepted/rejected.

### 10. Leaderboard
**Search**:
- Search bar at top to find a specific user by username.
- List filters automatically.

**Ranking Criteria**:
- Username
- Rides – total completed rides
- Distance (km) – total distance driven
- Money (€) – total earnings
- Rating – average user rating

**Sorting**:
- Click column headers to sort ascending/descending.

**Details**:
- Click a user to view rides and ratings.

### 11. Graphical Statistics
**Access**:
- Statistics page shows data for a current period (year or month).

**Chart Types**:
- Income
- Distance
- Ride Time
- Rating

**Modes**:
- Monthly – aggregated per month
- Daily – detailed daily data
- Filters adjust automatically depending on selection.

**Dynamic Updates**:
- Any filter or chart change updates instantly.

**Purpose**:
- Helps drivers, customers, and admins analyze trends, performance, and development.
