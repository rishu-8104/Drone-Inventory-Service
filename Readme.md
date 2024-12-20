# Drone Inventory Service

This service provides functionalities to manage a fleet of drones. Drones are represented by the `Drone` class, which has attributes such as ID, name, and capacity. The service allows users to perform operations like retrieving information about a specific drone, adding new drones to the fleet, updating drone details, removing drones, and fetching a list of all drones.

## Functionalities

### 1. Get Drone Information
   - **Endpoint:** `/control/drones/{id}`
   - **Method:** GET
   - **Example Request using curl:**
     ```
     curl http://localhost:8080/control/drones/1
     ```
   - **Example Response:**
     ```json
     {
       "id": "1",
       "name": "Drone1",
       "capacity": 120
     }
     ```

### 2. Get All Drones
   - **Endpoint:** `/control/drones/`
   - **Method:** GET
   - **Example Request using curl:**
     ```
     curl http://localhost:8080/control/drones/
     ```
   - **Example Response:**
     ```json
     [
       {
         "id": "1",
         "name": "Drone1",
         "capacity": 120
       },
       {
         "id": "2",
         "name": "Drone2",
         "capacity": 320
       },
       {
         "id": "3",
         "name": "Drone3",
         "capacity": 320
       }
     ]
     ```

### 3. Add New Drone
   - **Endpoint:** `/control/drones/`
   - **Method:** POST
   - **Example Request using curl:**
     ```
     curl -X POST -H "Content-Type: application/json" -d '{"id":"4", "name":"Drone4", "capacity": 200}' http://localhost:8080/control/drones/
     ```
   - **Example Response:**
     ```
     Added new drone to fleet: Drone4{id='4', name='Drone4', capacity=200}
     ```

### 4. Remove Drone
   - **Endpoint:** `/control/drones/{id}`
   - **Method:** DELETE
   - **Example Request using curl:**
     ```
     curl -X DELETE http://localhost:8080/control/drones/2
     ```
   - **Example Response:**
     ```
     Drone removed from fleet: 2
     ```

### 5. Update Drone
   - **Endpoint:** `/control/drones/`
   - **Method:** PUT
   - **Example Request using curl:**
     ```
     curl -X PUT -H "Content-Type: application/json" -d '{"id": "1", "name":"Drone1.v2", "capacity": 900}' http://localhost:8080/control/drones/
     ```
   - **Example Response:**
     ```
     Updated the drone: Drone{id='1', name='Drone1.v2', capacity=900}
     ```

### 6. Service Information
   - **Endpoint:** `/info`
   - **Method:** GET
   - **Example Request using curl:**
     ```
     curl http://localhost:8080/info
     ```
   - **Example Response:**
     ```
     Drone inventory ready
     ```
