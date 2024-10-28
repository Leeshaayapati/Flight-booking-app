# Sample flight data for demonstration
flights = [
    {"flight_id": 101, "origin": "New York", "destination": "London", "departure": "2024-11-01 10:00", "price": 500},
    {"flight_id": 102, "origin": "New York", "destination": "Paris", "departure": "2024-11-02 14:30", "price": 450},
    {"flight_id": 103, "origin": "London", "destination": "Dubai", "departure": "2024-11-03 22:00", "price": 600},
]

# Function to display available flights
def display_flights():
    print("Available flights:")
    for flight in flights:
        print(
            f"Flight ID: {flight['flight_id']} | Origin: {flight['origin']} | "
            f"Destination: {flight['destination']} | Departure: {flight['departure']} | Price: ${flight['price']}"
        )

# Function to book a flight
def book_flight():
    display_flights()
    try:
        flight_id = int(input("Enter the Flight ID of the flight you want to book: "))
        flight = next((f for f in flights if f["flight_id"] == flight_id), None)
        if not flight:
            print("Invalid Flight ID.")
            return

        # Collect passenger information
        passenger_name = input("Enter your name: ")
        num_tickets = int(input("Enter the number of tickets: "))

        # Calculate total cost
        total_cost = flight["price"] * num_tickets

        print(f"\nBooking Confirmation:")
        print(f"Passenger Name: {passenger_name}")
        print(f"Flight: {flight['origin']} to {flight['destination']}")
        print(f"Departure: {flight['departure']}")
        print(f"Number of Tickets: {num_tickets}")
        print(f"Total Cost: ${total_cost}")
        print("Your booking has been confirmed. Safe travels!")

    except ValueError:
        print("Invalid input. Please try again.")

# Main menu
def main():
    while True:
        print("\n--- Flight Booking System ---")
        print("1. View Available Flights")
        print("2. Book a Flight")
        print("3. Exit")
        choice = input("Enter your choice: ")
        
        if choice == "1":
            display_flights()
        elif choice == "2":
            book_flight()
        elif choice == "3":
            print("Thank you for using the Flight Booking System!")
            break
        else:
            print("Invalid choice. Please try again.")

# Run the main menu
if _name_ == "_main_":
    main()
