# Uber
Uber Management System in C++

#include<iostream>
#include <string>
//using namespace std;
using std::string;
class driver
{
private:
	string dname;
	string dcontact;
	string daddress;
	string dcnic;
	int trip;
	float drating;
public:
	driver();
	driver(string dname1, string dcontact1, string daddress1, string dcnic1, int trip1, float drating1);
	//~driver();
	void setdname(string dname1);
	void setdcontact(string dcontact1);
	void setdaddress(string daddress1);
	void setdcnic(string dcnic1);
	void settrip(int trip1);
	void setdrating(float drating1);
	string getdname();
	string getdcontact();
	string getdaddress();
	string getdcnic();
	int gettrip();
	float getdrating();
	void display();
};
class rider
{
private:
	//driver &bj_dri;
	string rname;
	string rcontact;
	float rrating;
	int trip_cancelled;
public:

	rider();
	rider(string rname1, string rcontact1, float rrating1, int trip_cancelled);
	//~driver();
	void setrname(string rname1);
	void setrcontact(string rcontact1);
	void settrip_cancelled(int trip1);
	void setrrating(float drating1);
	string getrname();
	string getrcontact();
	
	int gettrip_cancelled();
	float getrrating();
	void riderdisplay();

};
class ride : public driver, public rider
{
private:
	
	string pick_location;
	string destination;
	string vehicleNO;
	int tracking_id;
	string category;//(string, provided below)
	float base_fare;
	float per_km_charges;
	float per_min_charges;
	string promo_code;
	float discount;
	string start_time;// (preferably string that stores the time in 24hr clock e.g 1620 for 4:20PM)
	string arrival_time;// (preferably string that stores the time in 24hr
	float km;
	int min;
public:
	ride();
	ride( string pick_location, string destination, string vehicleNO, int tracking_id, string category, float base_fare, float per_km_charges, float per_min_charges, string promo_code, float discount, string start_time, string arrival_time);
	void setdriverobj(driver &obj1);
	void setriderobj(rider &s1);
	void setpick_location(string pick_location1);
	void setdestination(string destination1);
	void setvehicleNO(string vehicleNO1);
	void settracking_id(int tracking_id1);
	void setcategory(string category1);
	void setbase_fare(float base_fare1);
	void setper_km_charges(float per_km_charges1);
	void setper_min_charge(float per_min_charge1);
	void setpromo_code(string promo_code1);
	void setdiscount(float discount1);
	void setstart_time(string start_time1);
	void setarrival_time(string arrival_time1);
	double getcalbil();
	void set_total_km(float km);
	void set_total_min(int min);
	void displayride();

	void displayride2();
	double getcalbil2();

};
  
  
#include<iostream>
#include"Header.h"
#include<string>
//#define NULL 
using namespace std;
using std::string;

driver::driver()
{
	dname = "";
	dcontact = "";
	daddress = "";
	dcnic = "";
	trip = 0;
	drating= 0;
}
driver::driver(string dname1, string dcontact1, string daddress1, string dcnic1, int trip1, float drating1)
{
	dname = dname1;
	dcontact = dcontact1;
	daddress = daddress1;
	dcnic = dcnic1;
	trip = trip1;
	drating = drating1;
}

void driver::setdname(string dname1)
{
	dname = dname1;
	
}
void driver::setdcontact(string dcontact1)
{
	dcontact = dcontact1;
	
}
void driver::setdaddress(string daddress1)
{
	daddress = daddress1;
	
}
void driver::setdcnic(string dcnic1)
{
	dcnic = dcnic1;
	
}
void driver::settrip(int trip1)
{
	trip = trip1;
}
void driver::setdrating(float drating1)
{
	drating = drating1;

}
string driver::getdname()
{
	return dname;
}
string driver::getdcontact()
{
	return dcontact;
}
string driver::getdaddress()
{
	return daddress;
}
string driver::getdcnic()
{
	return dcnic;
}
int driver::gettrip()
{
	return trip;
}
float driver::getdrating()
{
	return drating;
}
void driver::display()
{
	cout << "Driver Name : " << getdname() << endl;
	cout << "Contact Number : " << getdcontact() << endl;
	cout << "Address of Driver : " << getdaddress() << endl;
	cout << "Driver Cnic : " << getdcnic() << endl;
	cout << "Trips : " << gettrip() << endl;
	cout << "Driver Rating " << getdrating() << endl;
}

rider::rider()
{
	rname = "";
	rcontact = "";
	trip_cancelled = 0;
	rrating = 0;
}
rider::rider(string rname1, string rcontact1, float rrating1, int trip_cancelled1)
{
	rname = rname1;
	rcontact = rcontact1;
	trip_cancelled = trip_cancelled1;
	rrating = rrating1;
}
void rider::setrname(string rname1)
{
	rname = rname1;

}
void rider::setrcontact(string rcontact1)
{
	rcontact = rcontact1;

}
void rider::settrip_cancelled(int trip_cancelled1)
{
	trip_cancelled = trip_cancelled1;
}
void rider::setrrating(float rrating1)
{
	rrating = rrating1;
}
string rider::getrname()
{
	return rname;
}
string rider::getrcontact()
{
	return rcontact;
}
int rider::gettrip_cancelled()
{
	return trip_cancelled;
}
float rider::getrrating()
{
	return rrating;
}
void rider::riderdisplay()
{
	cout << "Rider Name : " << getrname() << endl;
	cout << "Contact Number : " << getrcontact() << endl;
	cout << "Trips Cancelled : " << gettrip_cancelled() << endl;
	cout << "Rider Rating " << getrrating() << endl;
}
ride::ride()
{
	
	pick_location="";
	destination="";
	vehicleNO="";
	tracking_id=0;
	category="";//(string, provided below)
	base_fare=0;
	per_km_charges=0;
	per_min_charges = 0;
	promo_code = "";
	discount = 0;
	start_time = "";// (preferably string that stores the time in 24hr clock e.g 1620 for 4:20PM)
	arrival_time = "";
	km = 0;
	min = 0;

}
ride::ride(string pick_location1, string destination1, string vehicleNO1, int tracking_id1, string category1, float base_fare1, float per_km_charges1, float per_min_charges1, string promo_code1, float discount1, string start_time1, string arrival_time1)
{
	pick_location = pick_location1;
	destination = destination1;
	vehicleNO = vehicleNO1;
	tracking_id = tracking_id1;
	category = category1;
	base_fare = base_fare1;
	per_km_charges = per_km_charges1;
	per_min_charges = per_min_charges1;	
	promo_code = promo_code1;
	discount == discount1;
	start_time = start_time1;
	arrival_time = arrival_time1;

}
void ride::setdriverobj(driver &obj1)
{

}
void ride::setriderobj(rider &s1)
{

}
void ride::setpick_location(string pick_location1)
{
	pick_location = pick_location1;
	
}
void ride::setdestination(string destination1)
{
	destination = destination1;
	
}
void ride::setvehicleNO(string vehicleNO1)
{
	vehicleNO = vehicleNO1;
	
}
void ride::settracking_id(int tracking_id1)
{
	tracking_id = tracking_id1;
	
}
void ride::setcategory(string category1)
{
	category = category1;
	
}
void ride::setbase_fare(float base_fare1)
{
	base_fare = base_fare1;
	
}
void ride::setper_km_charges(float per_km_charges1)
{
	per_km_charges = per_km_charges1;
	
}
void ride::setper_min_charge(float per_min_charges1)
{
	per_min_charges = per_min_charges1;

}
void ride::setpromo_code(string promo_code1)
{
	promo_code = promo_code1;
}
void ride::setdiscount(float discount1)
{
	
	discount == discount1;
	
}
void ride::setstart_time(string start_time1)
{
	start_time = start_time1;
	
}
void ride::setarrival_time(string arrival_time1)
{
	arrival_time = arrival_time1;
}
void ride::set_total_km(float km1)
{
	km = km1;
}
void ride::set_total_min(int min1)
{
	min = min1;
}

double ride::getcalbil()
{
	double total = 0;
	double t = 0;
	if (promo_code == "pk8976")
	{
		total = (per_km_charges * km) + (per_min_charges * min);
		t = total / 4;
		total = total - t;
	}
	else
	{
		total = (per_km_charges * km) + (per_min_charges * min);
	}
	return total;
	
}
double ride::getcalbil2()

{
	double total = 0;
	double t = 0;
	if (promo_code == "pk8976")
	{
		total = base_fare + (per_km_charges * km) + (per_min_charges * min);
		t = total / 4;
		total = total - t;
	}
	else
	{
		total = base_fare + (per_km_charges * km) + (per_min_charges * min);
	}
	return total;
}
void ride::displayride()
{
	driver obj;
	rider s;
	cout << "Time  " << start_time << "   and   " << arrival_time << endl;
	cout << "Location  " << pick_location << "   and   " << destination << endl;
	cout << "Total Amount = " << getcalbil() <<endl;

	cout << "Driver Name : " << obj.getdname() << endl;
	cout << "Contact Number : " << obj.getdcontact() << endl;
	cout << "Address of Driver : " << obj.getdaddress() << endl;
	cout << "Driver Cnic : " << obj.getdcnic() << endl;
	cout << "Trips : " << obj.gettrip() << endl;
	cout << "Driver Rating " << obj.getdrating() << endl;
	//obj.display();
	cout << "Rider Name : " << s.getrname() << endl;
	cout << "Contact Number : " << s.getrcontact() << endl;
	cout << "Trips Cancelled : " << s.gettrip_cancelled() << endl;
	cout << "Rider Rating " << s.getrrating() << endl;
	//s.riderdisplay();
}
void ride::displayride2()
{
	driver obj;
	rider s;
	cout << "Time  " << start_time << "   and   " << arrival_time << endl;
	cout << "Location  " << pick_location << "   and   " << destination << endl;
	cout << "Total Amount = " << getcalbil2() << endl;;
	
	cout << "Driver Name : " << obj.getdname() << endl;
	cout << "Contact Number : " << obj.getdcontact() << endl;
	cout << "Address of Driver : " << obj.getdaddress() << endl;
	cout << "Driver Cnic : " << obj.getdcnic() << endl;
	cout << "Trips : " << obj.gettrip() << endl;
	cout << "Driver Rating " << obj.getdrating() << endl;
	//obj.display();
	cout << "Rider Name : " << s.getrname() << endl;
	cout << "Contact Number : " << s.getrcontact() << endl;
	cout << "Trips Cancelled : " << s.gettrip_cancelled() << endl;
	cout << "Rider Rating " << s.getrrating() << endl;
}
  
  #include<iostream>
#include"Header.h"
#include<string>
using namespace std;
//using std::string
int main()
{
	string dname= "Waleed";
	string dcontact="023023023032";
	string daddress="Nowshera";
	string dcnic="32332-32323333-2";
	int trip= 800;
	float drating=4.3;
	driver obj1(dname, dcontact, daddress, dcnic, trip, drating);
	obj1.setdname(dname);
	obj1.setdaddress(daddress);
	obj1.setdcontact(dcontact);
	obj1.setdcnic(dcnic);
	obj1.settrip(trip);
	obj1.setdrating(drating);
	obj1.display();
	cout << endl << endl;
	string rname = "Ahmad";
	string rcontact = "76466757755";
	int canceltrip = 5;
	float rracting = 2.8;
	rider s1(rname, rcontact, rracting, canceltrip);
	s1.setrname(rname);
	//s1.setdaddress(daddress);
	s1.setrcontact(rcontact);
	//obj1.setdcnic(dcnic);
	s1.settrip_cancelled(canceltrip);
	s1.setrrating(rracting);
	s1.riderdisplay();
	string op;
	cout << "Welcome   " << endl;
	cout << "Bike, Auto, Mini, Go, uberx" << endl;
	cin>>op;
	string pick_location= "Nowshera";
	string destination="Lahore";
	string vehicleNO= "lkl123";
	int tracking_id=37328;
	//string category;//(string, provided below)
	float base_fare;
	float per_km_charges;
	float per_min_charges;
	string promo_code;
	float discount=0;
	string start_time="4:45PM";
	string arrival_time="6:00PM";
	
	if (op == "Bike")
	{
		
		cout << "Promo code = " << endl;
		cin >> promo_code;
		//ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
		cout << "Enter 1 for base fare" << endl;
		cout << "Enter 2 for KM base Amount" << endl;
		cout << "Enter 3 for Minute base Amount" <<endl;
		int option = 0; 
		cin >> option;

		if (option == 1)
		{
			base_fare = 60;
			per_km_charges = 0;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			//cout << "Enter 1 for base fare" << endl;
			base_fare = 60;
			per_km_charges = 0;
			per_min_charges = 0;
			obj.getcalbil2();
			obj.displayride2();
		}
		else if (option == 2)
		{
			base_fare = 0;
			per_km_charges = 3.76;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_km(21);
			obj.getcalbil();
			obj.displayride();
		}
		else if (option == 3)
		{
			base_fare = 0;
			per_km_charges = 0;
			per_min_charges = 6.23;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_min(75);
			obj.getcalbil();
			obj.displayride();
		}
	}
	else if (op == "Auto")
	{
		
		cout << "Promo code = " << endl;
		cin >> promo_code;
		//ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
		cout << "Enter 1 for base fare" << endl;
		cout << "Enter 2 for KM base Amount" << endl;
		cout << "Enter 3 for Minute base Amount" << endl;
		int option = 0;
		cin >> option;
		if (option == 1)
		{
			base_fare = 50;
			per_km_charges = 0;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.getcalbil2();
			obj.displayride2();
		}
		else if (option == 2)
		{
			base_fare = 0;
			per_km_charges = 12.76;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_km(21);
			obj.getcalbil();
			obj.displayride();
		}
		else if (option == 3)
		{
			base_fare = 0;
			per_km_charges = 0;
			per_min_charges = 2.23;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_min(75);
			obj.getcalbil();
			obj.displayride();
		}

	}
	else if (op == "Mini")
	{
		cout << "Promo code = " << endl;
		cin >> promo_code;
		//ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
		cout << "Enter 1 for base fare" << endl;
		cout << "Enter 2 for KM base Amount" << endl;
		cout << "Enter 3 for Minute base Amount" << endl;
		int option = 0;
		cin >> option;
		if (option == 1)
		{
			base_fare = 60;
			per_km_charges = 3.76;
			per_min_charges = 6.23;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.getcalbil2();
			obj.displayride2();
		}
		else if (option == 2)
		{
			base_fare = 0;
			per_km_charges = 3.76;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_km(21);
			obj.getcalbil();
			obj.displayride();
		}
		else if (option == 3)
		{
			base_fare = 0;
			per_km_charges = 0;
			per_min_charges = 6.23;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_min(75);
			obj.getcalbil();
			obj.displayride();
		}

	}
	else if (op == "Go")
	{
		
		cout << "Promo code = " << endl;
		cin >> promo_code;
		//ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
		cout << "Enter 1 for base fare" << endl;
		cout << "Enter 2 for KM base Amount" << endl;
		cout << "Enter 3 for Minute base Amount" << endl;
		int option = 0;
		cin >> option;
		if (option == 1)
		{
			base_fare = 65;
			per_km_charges = 0;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.getcalbil2();
			obj.displayride2();
		}
		else if (option == 2)
		{
			base_fare = 0;
			per_km_charges = 8.76;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_km(21);
			obj.getcalbil();
			obj.displayride();
		}
		else if (option == 3)
		{
			base_fare = 0;
			per_km_charges = 0;
			per_min_charges = 3.23;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_min(75);
			obj.getcalbil();
			obj.displayride();
		}
	}
	else if (op == "uberx")
	{
		
		cout << "Promo code = " << endl;
		cin >> promo_code;
		//ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
		cout << "Enter 1 for base fare" << endl;
		cout << "Enter 2 for KM base Amount" << endl;
		cout << "Enter 3 for Minute base Amount" << endl;
		int option = 0;
		cin >> option;
		if (option == 1)
		{
			base_fare = 100;
			per_km_charges = 0;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.getcalbil2();
			obj.displayride2();
		}
		else if (option == 2)
		{
			base_fare = 0;
			per_km_charges = 15.76;
			per_min_charges = 0;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_km(21);
			obj.getcalbil();
			obj.displayride();
		}
		else if (option == 3)
		{
			base_fare = 0;
			per_km_charges = 0;
			per_min_charges = 8.23;
			ride obj(pick_location, destination, vehicleNO, tracking_id, op, base_fare, per_km_charges, per_min_charges, promo_code, discount, start_time, arrival_time);
			obj.set_total_min(75);
			obj.getcalbil();
			obj.displayride();
		}
	}

	else
	{
		cout << "Wrong entry " << endl;
	}
	return 0;
}
