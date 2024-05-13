# Travel_Data_Upload_and_Manipulating
 Data_Manipulation
 
CREATE TABLE booking(

    bookingid int primary key,
	contactid int,
	contactemail varchar,
	company varchar,
	membersales varchar,
	userid varchar,
	userregister_date varchar,
	environment varchar,
	booking_date varchar
)
;
COPY booking FROM 'C:\Users\seldabayman\Desktop\SQL_2_KOMUTLAR\booking.csv' DELIMITER ','CSV HEADER;

CREATE TABLE passenger (
	id int,
	bookingid int,
	gender varchar,
	name varchar,
	dateofbirth date
	
)
;
COPY passenger FROM '‪‪C:\Users\seldabayman\Desktop\passenger - Kopya.csv' DELIMITER ','CSV HEADER;

CREATE TABLE payment (
       id int,
	   bookingid int,
	   amount int,
	   cardtype varchar,
	   payment_status varchar,
	   cardnumber varchar,
	   payment_date varchar
)
;
COPY payment FROM '‪C:\Users\seldabayman\Desktop\SQL_2_KOMUTLAR\payment.csv' DELIMITER ',' CSV HEADER


ALTER TABLE passenger 
alter column dateofbirth type date 
using to_date (dateofbirth,'MM/DD/YY')

 ALTER TABLE payment
 alter column payment_date 
 type timestamp
 using to_timestamp (payment_date, 'MM/DD/YY HH24:MI');
 
 ALTER TABLE booking
 alter column booking_date 
 type timestamp
 using to_timestamp (booking_date, 'YY-MM-GG HH24:MI');

NOT: Copy ettiğiniz klasörün linkini kendi bilgisayaranızdaki dosyanın özellikler kısmından bakabilirsiniz.
 
