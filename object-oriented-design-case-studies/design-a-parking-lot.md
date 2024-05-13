<h1 align="center">Design a Parking Lot</h1>
<h3 align="center">Let's make an object-oriented design for a multi-floor Parking Lot</h3>

**We'll cover the following:**

- [System Requirements](#system-requirements)
- [Use Case Diagram](#use-case-diagram)
- [Class Diagram](#class-diagram)
- [Activity Diagram](#activity-diagram)
- [Code](#code)

A parking lot or car park is a dedicated cleared area that is intended for parking vehicles. In most countries where cars are a major mode of transportation, parking lots are a feature of every city and suburban area. Shopping malls, sports stadiums, megachurches, and similar venues often feature parking lots over large areas.

<p align="center">
    <img src="/media-files/parking-lot.png" alt="Parking Lot">
    <br />
    Parking Lot
</p>

### System Requirements

We will focus on the following set of requirements while designing the parking lot:

1. The parking lot should have multiple floors where customers can park their cars.
2. The parking lot should have multiple entry and exit points.
3. Customers can collect a parking ticket from the entry points and can pay the parking fee at the exit points on their way out.
4. Customers can pay the tickets at the automated exit panel or to the parking attendant.
5. Customers can pay via both cash and credit cards.
6. Customers should also be able to pay the parking fee at the customer’s info portal on each floor. If the customer has paid at the info portal, they don’t have to pay at the exit.
7. The system should not allow more vehicles than the maximum capacity of the parking lot. If the parking is full, the system should be able to show a message at the entrance panel and on the parking display board on the ground floor.
8. Each parking floor will have many parking spots. The system should support multiple types of parking spots such as Compact, Large, Handicapped, Motorcycle, etc.
9. The Parking lot should have some parking spots specified for electric cars. These spots should have an electric panel through which customers can pay and charge their vehicles.
10. The system should support parking for different types of vehicles like car, truck, van, motorcycle, etc.
11. Each parking floor should have a display board showing any free parking spot for each spot type.
12. The system should support a per-hour parking fee model. For example, customers have to pay $4 for the first hour, $3.5 for the second and third hours, and $2.5 for all the remaining hours.

### Use Case Diagram

Here are the main Actors in our system:

- **Admin:** Mainly responsible for adding and modifying parking floors, parking spots, entrance, and exit panels, adding/removing parking attendants, etc.
- **Customer:** All customers can get a parking ticket and pay for it.
- **Parking Attendant:** Parking attendants can do all the activities on the customer’s behalf, and can take cash for ticket payment.
- **System:** To display messages on different info panels, as well as assigning and removing a vehicle from a parking spot.

Here are the top use cases for Parking Lot:

- **Add/Remove/Edit parking floor:** To add, remove or modify a parking floor from the system. Each floor can have its own display board to show free parking spots.
- **Add/Remove/Edit parking spot:** To add, remove or modify a parking spot on a parking floor.
- **Add/Remove a parking attendant:** To add or remove a parking attendant from the system.
- **Take ticket:** To provide customers with a new parking ticket when entering the parking lot.
- **Scan ticket:** To scan a ticket to find out the total charge.
- **Credit card payment:** To pay the ticket fee with credit card.
- **Cash payment:** To pay the parking ticket through cash.
- **Add/Modify parking rate:** To allow admin to add or modify the hourly parking rate.

Here is the use case diagram of our Parking Lot:

<p align="center">
    <img src="/media-files/parking-use-case-diagram.svg" alt="Parking Lot Use Case Diagram">
    <br />
    Use Case Diagram for Parking Lot
</p>

### Class Diagram

Here are the main classes of our Parking Lot System:

- **ParkingLot:** The central part of the organization for which this software has been designed. It has attributes like ‘Name’ to distinguish it from any other parking lots and ‘Address’ to define its location.
- **ParkingFloor:** The parking lot will have many parking floors.
- **ParkingSpot:** Each parking floor will have many parking spots. Our system will support different parking spots 1) Handicapped, 2) Compact, 3) Large, 4) Motorcycle, and 5) Electric.
- **Account:** We will have two types of accounts in the system: one for an Admin, and the other for a parking attendant.
- **Parking ticket:** This class will encapsulate a parking ticket. Customers will take a ticket when they enter the parking lot.
- **Vehicle:** Vehicles will be parked in the parking spots. Our system will support different types of vehicles 1) Car, 2) Truck, 3) Electric, 4) Van and 5) Motorcycle.
- **EntrancePanel and ExitPanel:** EntrancePanel will print tickets, and ExitPanel will facilitate payment of the ticket fee.
- **Payment:** This class will be responsible for making payments. The system will support credit card and cash transactions.
- **ParkingRate:** This class will keep track of the hourly parking rates. It will specify a dollar amount for each hour. For example, for a two hour parking ticket, this class will define the cost for the first and the second hour.
- **ParkingDisplayBoard:** Each parking floor will have a display board to show available parking spots for each spot type. This class will be responsible for displaying the latest availability of free parking spots to the customers.
- **ParkingAttendantPortal:** This class will encapsulate all the operations that an attendant can perform, like scanning tickets and processing payments.
- **CustomerInfoPortal:** This class will encapsulate the info portal that customers use to pay for the parking ticket. Once paid, the info portal will update the ticket to keep track of the payment.
- **ElectricPanel:** Customers will use the electric panels to pay and charge their electric vehicles.

<p align="center">
    <img src="/media-files/parking-class-diagram.png" alt="Parking Lot Class Diagram">
    <br />
    Class Diagram for Parking Lot
</p>

<p align="center">
    <img src="/media-files/parking-uml.svg" alt="Parking Lot UML">
    <br />
    UML for Parking Lot
</p>

### Sequence Diagram

A sequence diagram is a great way to understand the interactions between different entities and objects in the system. There can be different sequence diagrams that we can create for our parking lot system. For the sake of this lesson, we will create sequence diagrams for the following two interactions:

- **Card payment:** This performs a payment using the card.

- **Sequence challenge:** This is for payment verification.

**Card payment**
The sequence diagram for the card payment should have the following actors and objects that will interact with each other:

**Actor:** Customer

**Object:** CardReader, Payment, and ExitPanel

Here are the steps in the card payment interaction:

- The customer inserts the card into the card reader.

- The card reader initiates a payment for the required parking fee.

- The payment processes the payment and returns the payment status.

* The card reader ejects the card.

If the payment is successful:

- The customer requests a receipt for the transaction.

- The exit panel prints a receipt for the customer.

If the payment is unsuccessful:

- The customer sees an error message for an unsuccessful Payment.

<p align="center">
    <img src="/media-files/sequence-diagram for-card-payment-at-the-Parking-Lot.png" alt="Sequence Diagram for card payment">
    <br />
    Sequence Diagram for card payment
</p>

**Sequence challenge: Payment verification**
The skeleton below represents the payment verification sequence diagram. Here the payment status of the ticket is currently unpaid and the parking fee has to be calculated.

<p align="center">
    <img src="/media-files/sequence-diagram-for-payment-verification.png" alt="Sequence Diagram for payment verification">
    <br />
    Sequence Diagram for payment verification
</p>

### Activity Diagram

An activity diagram is a great way to visualize the flow of messages from one activity to the other in the system. There can be different activity diagrams that we can create for our parking lot system. For this lesson, we will create activity diagrams for the following two activities:

- The vehicle entering the parking lot

- Customer pays the parking ticket

**The vehicle entering the parking lot**

Vehicle entering the parking lot#
The following are the states and actions that will be involved in this activity diagram.

**States**

- Initial state: The customer enters the parking lot.

- Final state: There are two final states present in this activity diagram, shown below:

- The customer receives the parking ticket through the system.

- There is no parking slot vacant, so the customer is denied access to the parking lot.

**Actions**
The customer arrives at the parking lot entrance and selects their vehicle type. They are assigned their dedicated parking spot according to their select vehicle type. The parking lot then informs us about the availability of that parking spot and allows access accordingly.

<p align="center">
    <img src="/media-files/activity-diagram-for-vehicle-entering-a-parking-lot.png" alt="Activity Diagram for vehicle entering the parking lot">
    <br />
    Activity Diagram for vehicle entering the Parking Lot
</p>

**Customer paying for parking ticket:** Any customer can perform this activity. Here are the set of steps:

<p align="center">
    <img src="/media-files/parking-ticket.svg" alt="Parking Ticket Activity Diagram">
    <br />
    Activity Diagram for Parking Lot Parking Ticket
</p>

### Code

Following is the skeleton code for our parking lot system:

**Enums and Constants:** Here are the required enums, data types, and constants:
First of all, we will define all the enumerations required in the parking lot. According to the class diagram, there are two enumerations used in the system i.e., PaymentStatus and AccountStatus.

```java

// Enumeration
enum PaymentStatus {
  COMPLETED,
  FAILED,
  PENDING,
  UNPAID,
  REFUNDED
}

enum AccountStatus {
  ACTIVE,
  CLOSED,
  CANCELED,
  BLACKLISTED,
  NONE
}

// Custom Person data type class
public class Person {
  private String name;
  private String address;
  private String phone;
  private String email;
}

// Custom Address data type class
public class Address {
  private int zipCode;
  private String address;
  private String city;
  private String state;
  private String country;
}

```

**Account, Admin, and ParkingAttendant:** These classes represent various people that interact with our system.
The Account class will be an abstract class, which will have the actors, Admin and ParkingAttendant, as child classes.

```java
public abstract class Account {
  // Data members
  private String userName;
  private String password;
  private Person person; // Refers to an instance of the Person class
  private AccountStatus status; // Refers to the AccountStatus enum

  public abstract boolean resetPassword();
}

public class Admin extends Account {
  // spot here refers to an instance of the ParkingSpot class
  public boolean addParkingSpot(ParkingSpot spot);
  // displayBoard here refers to an instance of the DisplayBoard class
  public boolean addDisplayBoard(DisplayBoard displayBoard);
  // entrance here refers to an instance of the Entrance class
  public boolean addEntrance(Entrance entrance);
  // exit here refers to an instance of the Exit class
  public boolean addExit(Exit exit);

  // Will implement the functionality in this class
  public boolean resetPassword() {
    // definition
  }
}

public class ParkingAttendant extends Account {
  public boolean processTicket(String ticketNumber);

  // Will implement the functionality in this class
  public boolean resetPassword() {
    // definition
  }
}

```

**ParkingSpot:** Here is the definition of ParkingSpot and all of its children classes:

```java

// ParkingSpot is an abstract class
public abstract class ParkingSpot {
  private int id;
  private boolean isFree;
  private Vehicle vehicle;

  public boolean getIsFree();
  public abstract boolean assignVehicle(Vehicle vehicle);
  public boolean removeVehicle(){
    // definition
  }
}

public class Handicapped extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

public class Compact extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

public class Large extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

public class Motorcycle extends ParkingSpot {
  public boolean assignVehicle(Vehicle vehicle) {
    // definition
  }
}

```

**Vehicle:**Vehicle will be another abstract class, which serves as a parent for four different types of vehicles: car, truck, van, and motor cycle.

```java
// Vehicle is an abstract class
public abstract class Vehicle {
  private int licenseNo;
  public abstract void assignTicket(ParkingTicket ticket);
}

public class Car extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}

public class Van extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}

public class Truck extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}

public class MotorCycle extends Vehicle {
  public void assignTicket(ParkingTicket ticket) {
    // definition
  }
}
```

**ParkingFloor:** This class encapsulates a parking floor:

```java
import java.util.HashMap;

class ParkingFloor {
    private String __name;
    private HashMap<Integer, ParkingSpot> __handicapped_spots;
    private HashMap<Integer, ParkingSpot> __compact_spots;
    private HashMap<Integer, ParkingSpot> __large_spots;
    private HashMap<Integer, ParkingSpot> __motorbike_spots;
    private HashMap<Integer, ParkingSpot> __electric_spots;
    private HashMap<Integer, ParkingInfoPortal> __info_portals;
    private HashMap<String, Integer> __free_handicapped_spot_count;
    private HashMap<String, Integer> __free_compact_spot_count;
    private HashMap<String, Integer> __free_large_spot_count;
    private HashMap<String, Integer> __free_motorbike_spot_count;
    private HashMap<String, Integer> __free_electric_spot_count;
    private ParkingDisplayBoard __display_board;

    public ParkingFloor(String name) {
        this.__name = name;
        this.__handicapped_spots = new HashMap<>();
        this.__compact_spots = new HashMap<>();
        this.__large_spots = new HashMap<>();
        this.__motorbike_spots = new HashMap<>();
        this.__electric_spots = new HashMap<>();
        this.__info_portals = new HashMap<>();
        this.__free_handicapped_spot_count = new HashMap<>();
        this.__free_handicapped_spot_count.put("free_spot", 0);
        this.__free_compact_spot_count = new HashMap<>();
        this.__free_compact_spot_count.put("free_spot", 0);
        this.__free_large_spot_count = new HashMap<>();
        this.__free_large_spot_count.put("free_spot", 0);
        this.__free_motorbike_spot_count = new HashMap<>();
        this.__free_motorbike_spot_count.put("free_spot", 0);
        this.__free_electric_spot_count = new HashMap<>();
        this.__free_electric_spot_count.put("free_spot", 0);
        this.__display_board = new ParkingDisplayBoard();
    }

    public void add_parking_spot(ParkingSpot spot) {
        switch (spot.get_type()) {
            case ParkingSpotType.HANDICAPPED:
                this.__handicapped_spots.put(spot.get_number(), spot);
                break;
            case ParkingSpotType.COMPACT:
                this.__compact_spots.put(spot.get_number(), spot);
                break;
            case ParkingSpotType.LARGE:
                this.__large_spots.put(spot.get_number(), spot);
                break;
            case ParkingSpotType.MOTORBIKE:
                this.__motorbike_spots.put(spot.get_number(), spot);
                break;
            case ParkingSpotType.ELECTRIC:
                this.__electric_spots.put(spot.get_number(), spot);
                break;
            default:
                System.out.println("Wrong parking spot type");
        }
    }

    public void assign_vehicleToSpot(Vehicle vehicle, ParkingSpot spot) {
        spot.assign_vehicle(vehicle);
        switch (spot.get_type()) {
            case ParkingSpotType.HANDICAPPED:
                update_display_board_for_handicapped(spot);
                break;
            case ParkingSpotType.COMPACT:
                update_display_board_for_compact(spot);
                break;
            case ParkingSpotType.LARGE:
                update_display_board_for_large(spot);
                break;
            case ParkingSpotType.MOTORBIKE:
                update_display_board_for_motorbike(spot);
                break;
            case ParkingSpotType.ELECTRIC:
                update_display_board_for_electric(spot);
                break;
            default:
                System.out.println("Wrong parking spot type!");
        }
    }

    private void update_display_board_for_handicapped(ParkingSpot spot) {
        if (this.__display_board.get_handicapped_free_spot().get_number() == spot.get_number()) {
            // find another free handicapped parking and assign to display_board
            for (int key : this.__handicapped_spots.keySet()) {
                if (this.__handicapped_spots.get(key).is_free()) {
                    this.__display_board.set_handicapped_free_spot(this.__handicapped_spots.get(key));
                    break;
                }
            }
            this.__display_board.show_empty_spot_number();
        }
    }

    private void update_display_board_for_compact(ParkingSpot spot) {
        if (this.__display_board.get_compact_free_spot().get_number() == spot.get_number()) {
            // find another free compact parking and assign to display_board
            for (int key : this.__compact_spots.keySet()) {
                if (this.__compact_spots.get(key).is_free()) {
                    this.__display_board.set_compact_free_spot(this.__compact_spots.get(key));
                    break;
                }
            }
            this.__display_board.show_empty_spot_number();
        }
    }

    public void free_spot(ParkingSpot spot) {
        spot.remove_vehicle();
        switch (spot.get_type()) {
            case ParkingSpotType.HANDICAPPED:
                this.__free_handicapped_spot_count.put("free_spot", this.__free_handicapped_spot_count.get("free_spot") + 1);
                break;
            case ParkingSpotType.COMPACT:
                this.__free_compact_spot_count.put("free_spot", this.__free_compact_spot_count.get("free_spot") + 1);
                break;
            case ParkingSpotType.LARGE:
                this.__free_large_spot_count.put("free_spot", this.__free_large_spot_count.get("free_spot") + 1);
                break;
            case ParkingSpotType.MOTORBIKE:
                this.__free_motorbike_spot_count.put("free_spot", this.__free_motorbike_spot_count.get("free_spot") + 1);
                break;
            case ParkingSpotType.ELECTRIC:
                this.__free_electric_spot_count.put("free_spot", this.__free_electric_spot_count.get("free_spot") + 1);
                break;
            default:
                System.out.println("Wrong parking spot type!");
        }
    }
}

```

**ParkingDisplayBoard:** This class encapsulates a parking display board:

```java
public class DisplayBoard {
  // Data members
  private int id;
  private Map<String, List<ParkingSpot>> parkingSpots;

  // Constructor
  public DisplayBoard(int id) {
    this.id = id;
    this.parkingSpots = new HashMap<>();
  }

  // Member function
  public void addParkingSpot(String spotType, List<ParkingSpot> spots);
  public void showFreeSlot(){

    StringBuilder message = new StringBuilder();
    if (this.__handicappedFreeSpot.isFree()) {
        message.append("Free Handicapped: ").append(this.__handicappedFreeSpot.getNumber());
    } else {
        message.append("Handicapped is full");
    }
    message.append("\n");

    if (this.__compactFreeSpot.isFree()) {
        message.append("Free Compact: ").append(this.__compactFreeSpot.getNumber());
    } else {
        message.append("Compact is full");
    }
    message.append("\n");

    if (this.__largeFreeSpot.isFree()) {
        message.append("Free Large: ").append(this.__largeFreeSpot.getNumber());
    } else {
        message.append("Large is full");
    }
    message.append("\n");

    if (this.__motorbikeFreeSpot.isFree()) {
        message.append("Free Motorbike: ").append(this.__motorbikeFreeSpot.getNumber());
    } else {
        message.append("Motorbike is full");
    }
    message.append("\n");

    if (this.__electricFreeSpot.isFree()) {
        message.append("Free Electric: ").append(this.__electricFreeSpot.getNumber());
    } else {
        message.append("Electric is full");
    }

    System.out.println(message.toString());
  };
}

public class ParkingRate {
  // Data members
  private double hours;
  private double rate;

  // Member function
  public void calculate();
}
```

**Entrance and exit**
This section contains the Entrance and Exit classes, both of which are associated with the ParkingTicket class.

```java
public class Entrance {
  // Data members
  private int id;

  // Member function
  public ParkingTicket getTicket();
}

public class Exit {
  // Data members
  private int id;

  // Member function
  public void validateTicket(ParkingTicket ticket){
    // Perform validation logic for the parking ticket
    // Calculate parking charges, if necessary
    // Handle the exit process
  }
}
```

**Parking ticket**
The definition of the ParkingTicket class can be found below. This contains instances of the Vehicle, Payment, Entrance and Exit classes:

```java
public class ParkingTicket {
    private int ticketNo;
    private Date timestamp;
    private Date exit;
    private double amount;
    private boolean status;

    // Following are the instances of their respective classes
    private Vehicle vehicle;
    private Payment payment;
    private Entrance entrance;
    private Exit exitIns;
}
```

**Payment**
The Payment class is another abstract class, with the Cash and CreditCard classes as its child. This takes the PaymentStatus enumeration and the dateTime data type to keep track of the payment status and time.

```java
// Payment is an abstract class
public abstract class Payment {
    private double amount;
    private PaymentStatus status;
    private Date timestamp;

    public abstract boolean initiateTransaction();
}

public class Cash extends Payment {
    public boolean initiateTransaction() {
        // definition
    }
}

public class CreditCard extends Payment {
    public boolean initiateTransaction() {
        // definition
    }
}
```

**ParkingLot:** Our system will have only one object of this class. This can be enforced by using the [Singleton](https://en.wikipedia.org/wiki/Singleton_pattern) pattern. In software engineering, the singleton pattern is a software design pattern that restricts the instantiation of a class to only one object.

```java

public class ParkingLot {
    # singleton ParkingLot to ensure only one object of ParkingLot in the system,
    # all entrance panels will use this object to create new parking ticket: get_new_parking_ticket(),
    # similarly exit panels will also use this object to close parking tickets
    instance = None
    private int id;
    private String name;
    private String address;
    private ParkingRate parkingRate;

    private HashMap<String, Entrance> entrance;
    private HashMap<String, Exit> exit;

    // Create a hashmap that identifies all currently generated tickets using their ticket number
    private HashMap<String, ParkingTicket> tickets;

    // The ParkingLot is a singleton class that ensures it will have only one active instance at a time
    // Both the Entrance and Exit classes use this class to create and close parking tickets
    private static ParkingLot parkingLot = null;

    // Created a private constructor to add a restriction (due to Singleton)
    private ParkingLot() {
        // Call the name, address and parking_rate
        // Create initial entrance and exit hashmaps respectively
    }

    // Created a static method to access the singleton instance of ParkingLot
    public static ParkingLot getInstance() {
        if (parkingLot == null) {
            parkingLot = new ParkingLot();
        }
        return parkingLot;
    }

    public boolean addEntrance(Entrance entrance){}
    public boolean addExit(Exit exit){}

    // This function allows parking tickets to be available at multiple entrances
    public ParkingTicket getParkingTicket(Vehicle vehicle) {}

    public boolean isFull(ParkingSpot type){}
}

```
