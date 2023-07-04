import java.util.Scanner;

public class ReservationSystem {
    static Scanner scanner = new Scanner(System.in);

    public static void main(String[] args) 
    {
        System.out.println("Welcome to the Online Reservation System!");
        login();
    }

    static void login() 
    {
        System.out.print("Enter username: ");
        String username = scanner.nextLine();
        System.out.print("Enter password: ");
        String password = scanner.nextLine();

        if (isValid(username, password)) 
        {
            System.out.println("Login successful!");
            reservation();
        } 
        else 
        {
            System.out.println("Invalid username or password. Try again.");
            login();
        }
    }

    static void reservation() 
    {
        System.out.println("Reservation Form");
        System.out.println("Enter your name: ");
        String name = scanner.nextLine();
        System.out.print("Enter train number: ");
        int trainNumber = scanner.nextInt();
        scanner.nextLine(); 
        System.out.print("Enter class type: ");
        String classType = scanner.nextLine();
        System.out.print("Enter date of journey: ");
        String date = scanner.nextLine();
        System.out.print("Enter from (place): ");
        String from = scanner.nextLine();
        System.out.print("Enter to (destination): ");
        String to = scanner.nextLine();
        saveReservation(name, trainNumber, classType, date, from, to);

        System.out.println("Reservation successful!");
        System.out.println("Press 1 to make another reservation or \n press 2 to cancel a reservation.");
        int choice = scanner.nextInt();
        scanner.nextLine(); 
        if (choice == 1) 
        {
            reservation();
        } 
        else if (choice == 2) 
        {
            cancellation();
        } 
        else 
        {
            System.out.println("Invalid choice. Exiting program.");
        }
    }

    static void cancellation() 
    {
        System.out.println("Cancellation Form");
        System.out.print("Enter PNR number: ");
        int pnr = scanner.nextInt();
        System.out.println("Your Train Details are:");
        
        String reservation = getReservation(pnr);

        if (reservation != null) 
        {
            System.out.println("Are you sure you want to cancel this reservation?");
            System.out.println(reservation);
            System.out.println("Press Y for Yes or N for No: ");
            String choice = scanner.next();

            if (choice.equalsIgnoreCase("Y")) 
            {
         
                deleteReservation(pnr);
                System.out.println("Reservation cancelled.");
            } 
            else 
            {
                System.out.println("Reservation not cancelled.");
            }
        } 
        else 
        {
            System.out.println("Reservation not found.");
        }

        System.out.println("Press 1 to make another reservation or 2 to exit program.");
        int option = scanner.nextInt();
        scanner.nextLine(); 
        if (option == 1) 
        {
            reservation();
        } 
        else 
        {
            System.out.println("Exiting program.");
        }
    }
    static boolean isValid(String username, String password) 
    {
    
        return true;
    }

    static void saveReservation(String name, int trainNumber, String classType, String date, String from, String to)
    {

    }

    static String getReservation(int pnr)
    {
      
        return "1234";
    }
    
    static void deleteReservation(int pnr){
        

    }
    
}