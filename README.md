Description
 
 
 
 Hotel Reservation - Total Bill Calculation
 
Click here to download the Code Skeleton
 
Golden Star Hills is one of the most widely used resorts in the state. They need a system that can be configured easily to adapt to the changes they bring in with the charges for the room type and need to calculate the total bill for their customers. You being their software consultant have been approached by them to develop a software system which can be used for managing their business.  
Service: Calculating the Total bill for each customer
Create an Invoice class with the below private attributes

 
reservationId
	
String


stayDaysCount
	
int


roomCharge
	
RoomChargeInfo


gstPercentage
	
int
 
Include getter and setter methods for all the above attributes. The invoice class should be registered as a bean with the spring container via XML file.
The value for gstPercentage is populated in the charges.properties file as key=value pair. Fetch the values from the property file and assign them to the private attribute gstPercentage in the Invoice class. The values for these attributes should be injected via setter based injection. Do not change the value of gstPercentage in the property file.
Note: GST 12 percentage
Create a RoomChargeInfo class with the below private attribute
roomCharges
	
Map<String, Float>
 
Include getter and setter methods for the above attribute.
The Map should be configured in the beans.xml file with the below key-values.
Key-Room Type (String)
	
Value-Room Charge (Float)


Deluxe
	
3500.0


UltraDeluxe
	
7000.0


SuperDeluxe
	
8750.0
 
Note: Only for these roomType GST charges need to be added to the billAmount. The keys are case-sensitive.
RoomChargeInfo is used for only particular property, so RoomChargeInfo should be declared as an inner bean in the Invoice class. RoomChargeInfo should be injected into the Invoice via setter based Injection.
Overview of Service 1:
Write a method public double calculateTotalBill (Invoice invoiceObj, String roomType) in InvoiceBO class that accepts a string and Invoice Object. The string contains the type of room. Based on the roomType, GST needs to be added to the total bill and return the billAmount. If the type of room is not available on the Map then there is no GST charge.
The formula to calculate the total bill amount is given below:
If the type of room is available in the map then the calculation should be as follows,
total = stayDaysCount  *  roomCharge;
totalBillAmount = total + (total * gstPercentage / 100.0);
If the type of room is not available on the map then the calculation should be as follows,
totalBillAmount = stayDaysCount * 1000;
Technical Specifications:
Component Name
	
Method Name
	
Input
	
Output
	
Exception


InvoiceService
	
calculateTotalBill()
	
String reservationId,
int stayDaysCount,
String roomType
	
double - totalBillAmount
	
InvalidStayDaysCountException
This Exception is to be  thrown back to the Driver class


InvoiceBO
	
calculateTotalBill()
	
Invoice invoiceObj, String roomType
	
double - totalBillAmount
	
 


beans.xml
	
Contains all the xml configurations related to Service 
	
 
	
 
	
 
 
Create a class called Driver with the main method and get the inputs like reservationId, number of days stayed by the customer and type of room from the user. Get the InvoiceService class object from the beans.xml file and invoke the calculateTotalBill (String reservationId, int stayDaysCount, String roomType) which is in the InvoiceService class to perform the implementation. Display the total bill amount which is returned from the calculateTotalBill method in InvoiceBO class.
Business Rules & Validations:
In InvoiceService class include the following private attribute and inject via setter based injection.
private InvoiceBO invoiceBoObj;
 Include getter and setter methods for the above attribute.
 
In this InvoiceService class, the method public double calculateTotalBill (String reservationId, int stayDaysCount, String roomType) accepts reservationId, stayDaysCount, and roomType as the arguments. Validate the stayDaysCount, if the stay days count is within the range,  get the Invoice object from the beans.xml file and set the stayDaysCount and reservationId in that object.
In case the stayDaysCount is not within the range, a user-defined Exception InvalidStayDaysCountException should be thrown with the message "Days Stayed is not valid".
Days stayed should be greater than zero (0) and less than thirty (30).
If the days stayed are within the given range, call the method calculateTotalBill (Invoice invoiceObj, String roomType) in InvoiceBO class and perform the implementation.
Limitations and Constraints
1.      Invoice and RoomChargeInfo class should be in com.spring.model package.
2.      InvalidStayDaysCountException class should be in com.spring.exception package.
3.      InvoiceService class should be in com.spring.service package.
4.      InvoiceBO class should be in com.spring.bo package.
5.      Driver class should be in com.spring.main package.
6.      All of the above mentioned java classes to be configured as beans in the beans.xml file
7.      RoomChargeInfo should be declared as an inner bean in the Invoice class and should be injected into Invoice via setter based Injection.
8.      InvoiceService should be configured as bean inside beans.xml.
9.      InvoiceBO should be configured as bean inside beans.xml with the bean id as "inBoObj"
10.  InvoiceBO should be injected via setter based injection inside InvoiceService
11.  The room charge for each room type should be declared as a MAP in the beans.xml and should be injected using a setter.
12.  charges.properties file will be provided with the value for GST percentage fetch and assign values for the gstPercentage attribute in the Invoice class via setter based injection. To read this property file use <context:property-placeholder location="classpath:charges.properties" /> in the beans.xml file.
13.  DO NOT change the values in the charges.properties file
14.  Use ONLY beans.xml for all configurations.
 
Sample Input Output 1:
Enter the Reservation ID:
GSH101
Enter the total days stayed:
3
Enter the type of room stayed:
Deluxe  // Room type is available on the Map hence GST is Applicable
Total amount to be paid:11760.0


Sample Input Output 2:
Enter the Reservation ID:
GSH102
Enter the total days stayed:
2
Enter the type of room stayed:
UltraDeluxe  // Room type is available in the Map hence GST is Applicable
Total amount to be paid:15680.0


Sample Input Output 3:
Enter the Reservation ID:
GSH103
Enter the total days stayed:
31 // Days Stayed is not in a given range
Enter the type of room stayed:
UltraDeluxe  // Room type is available in the Map hence GST is Applicable
Days Stayed is not valid


Sample Input Output 4:
Enter the Reservation ID:
GSH107
Enter the total days stayed:
2
Enter the type of room stayed:
Normal  // Room type is not available on the Map hence NO GST
Total amount to be paid:2000.0


Sample Input Output 5:
Enter the Reservation ID:
GSH112
Enter the total days stayed:
4
Enter the type of room stayed:
SuperDeluxe  // Room type is available in the Map hence GST is Applicable
Total amount to be paid:39200.0
