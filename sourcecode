#include<iostream>
using namespace std;
struct flight {
	string F_name, source, dest, arrtime, depttime, status;
};
struct Dos_arr {
	flight newflight;
	Dos_arr* dos_arr_next;
};
struct Dos_Dept {
	flight newflight;
	Dos_arr* dos_dept_next;
};
struct int_arr {
	flight newflight;
	int_arr* int_arr_next;
};
struct int_Dept {
	flight newflight;
	int_Dept* int_dept_next;
};
struct stack {
	flight newflight;
	stack *next;
};
//declaring dif pointers
Dos_arr* dshead = NULL;
Dos_arr* dstail = NULL;
int_arr* iahead = NULL;
int_arr* iatail = NULL;
Dos_Dept* ddhead = NULL;
Dos_Dept* ddtail = NULL;
int_Dept* idhead = NULL;
int_Dept* idtail = NULL;
stack* head;

///function prototypes
int display();
int insert();
int tobelandeddisplay();
int alreadylanded();
int remove();
int changeflightstatus();
void pushtostack(string F_name, string source, string dest, string arrtime, string depttime, string status);

int main() {
	int a = 0;
	do { system("pause"); a = display(); } while (a);

}
int display() {
	int choice = 0; int toexit = 1;
	while (toexit) {
		system("cls");
		toexit = 0;
		cout << "Welcome to flight management system " << endl;
		cout << "Enter 1 to reserve a slot for flight landings: " << endl;
		cout << "Enter 2 to view all flight scedule to be landed: " << endl;
		cout << "Enter 3 view all the flights already landed sucesfully: " << endl;
		cout << "Enter 4 to change flight status : " << endl;
		cout << "Enter 5 to Exit " << endl;
		cin >> choice;
		switch (choice)
		{ 
		case 1: {system("cls"); toexit = insert(); break; }
		case 2: {system("cls"); toexit = tobelandeddisplay(); break; }
		case 3: {system("cls"); toexit = alreadylanded(); break; }
		case 4: {system("cls"); toexit = changeflightstatus(); break; }
		case 5: {system("cls"); cout << "Closing the Program"; system("pause"); exit(0); break; }
		}//switch

	}//while
	return toexit;
}//funt
int insert() {
	int r;

	flight* temp = new flight;
	cout << "Enter the flight details to add " << endl;
	cout << "Flight name: "; cin >> temp->F_name;
	cout << "Flight source:(int/dom) "; cin >> temp->source;
	cout << "Flight destination: "; cin >> temp->dest;
	cout << "Flight arrival time: "; cin >> temp->arrtime;
	cout << "Flight departure time: "; cin >> temp->depttime;
	cout << "Flight Status: "; cin >> temp->status;
	if (temp->source == "int")
	{
		int_arr* list = new int_arr;

		if (iahead == NULL)
		{
			
			list->newflight.F_name = temp->F_name;
			list->newflight.source = temp->source;
			list->newflight.dest = temp->dest;
			list->newflight.arrtime = temp->arrtime;
			list->newflight.depttime = temp->depttime;
			list->newflight.status = temp->status;
			list->int_arr_next = NULL;
			iahead = list;
			iatail = list;


		}
		else {
			iatail->int_arr_next = list;
			iatail->int_arr_next->newflight.F_name = temp->F_name;
			iatail->int_arr_next->newflight.source = temp->source;
			iatail->int_arr_next->newflight.dest = temp->dest;
			iatail->int_arr_next->newflight.arrtime = temp->arrtime;
			iatail->int_arr_next->newflight.depttime = temp->depttime;
			iatail->int_arr_next->newflight.status = temp->status;
			iatail->int_arr_next = list;
			iatail = list;

		}
	}//if
	else {
		Dos_arr *list=new Dos_arr;
		if (dshead == NULL)
		{
			list->newflight.F_name = temp->F_name;
			list->newflight.source = temp->source;
			list->newflight.dest = temp->dest;
			list->newflight.arrtime = temp->arrtime;
			list->newflight.depttime = temp->depttime;
			list->newflight.status = temp->status;
			list->dos_arr_next = NULL;
			dshead=list;
			dstail = dshead;


		}
		else {
			dstail->dos_arr_next = list;
			
			dstail->dos_arr_next->newflight.F_name = temp->F_name;
			dstail->dos_arr_next->newflight.source = temp->source;
			dstail->dos_arr_next->newflight.dest = temp->dest;
			dstail->dos_arr_next->newflight.arrtime = temp->arrtime;
			dstail->dos_arr_next->newflight.depttime = temp->depttime;
			dstail->dos_arr_next->newflight.status = temp->status;
			dstail->dos_arr_next->dos_arr_next = NULL;
			dstail = list;

		}
	} system("cls");
	cout << "Flight is Added..Do you want to perform another operation:(Y:1/N:0)"; cin >> r; 	return r;
}
int tobelandeddisplay() {
	int count=0;
	flight* temp = new flight;
	int_arr* temp_iar=iahead;
	cout << "international flights are followings: " << endl;
	while (temp_iar!= NULL) {
		cout << "The flights details are following: ";
		cout << "Flight name: " << temp_iar->newflight.F_name << endl;
		cout << "Flight source: " << temp_iar->newflight.source << endl;
		cout << "Flight destination: " << temp_iar->newflight.dest << endl;
		cout << "Flight arrival time: " << temp_iar->newflight.arrtime << endl;
		cout << "Flight departure time: " << temp_iar->newflight.depttime << endl;
		cout << "Flight status: " << temp_iar->newflight.status << endl;
		cout << "---------------------Details completed------------------" << endl;
		count++;
		temp_iar = temp_iar->int_arr_next;
	}
	temp_iar = NULL;
	delete temp_iar;
	if (count == 0)
		cout << "There are no international flights." << endl;
	count = 0;
	Dos_arr* temp_dsr = dshead;
	while (temp_dsr != NULL) {
		cout << "The flights details are following: " << endl;
		cout << "Flight name: " << temp_dsr->newflight.F_name << endl;
		cout << "Flight source: " << temp_dsr->newflight.source << endl;
		cout << "Flight destination: " << temp_dsr->newflight.dest << endl;
		cout << "Flight arrival time: " << temp_dsr->newflight.arrtime << endl;
		cout << "Flight dept time: " << temp_dsr->newflight.depttime << endl;
		cout << "Flight status: " << temp_dsr->newflight.status << endl;
		cout<<"-----------------details are completed-------------" << endl;
		count++;
		temp_dsr = temp_dsr->dos_arr_next;
	}int tttt;
	cout << "do you want to perform any other function (Y:1/N:0) :"; cin >> tttt;
	return tttt;
}
int changeflightstatus() {
	string tname;
	cout << "Enter flight name to change status: " << endl; cin >> tname;
	int count = 0;
	flight* temp = new flight;
	int_arr* temp_iar = iahead;
	int_arr* temp_iarR=iahead;
	
	while (count != 1 ) {
		if (temp_iar->newflight.F_name == tname) {
			cout << "The flights details are following: " << endl;
			cout << "Flight name: " << temp_iar->newflight.F_name << endl;
			cout << "Flight source: " << temp_iar->newflight.source << endl;
			cout << "Flight destination: " << temp_iar->newflight.dest << endl;
			cout << "Flight arrival time: " << temp_iar->newflight.arrtime << endl;
			cout << "Flight departure time: " << temp_iar->newflight.depttime << endl;
			cout << "Flight status: " << temp_iar->newflight.status << endl;
			cout << "Update Flight Status to landed: ";  temp_iar->newflight.status = "Landed";
			pushtostack(temp_iar->newflight.F_name, temp_iar->newflight.source, temp_iar->newflight.dest, temp_iar->newflight.arrtime, temp_iar->newflight.depttime, temp_iar->newflight.status);
			temp_iarR->int_arr_next = temp_iar->int_arr_next;
			delete temp_iar;
			count++;
		}
		else {
			temp_iarR;
			temp_iar = temp_iar->int_arr_next;
		}
			if (count != 0)
			{
				cout << "testing";
			}
			else if (count == 0) {
				Dos_arr* temp_dsr = dshead;
				while (temp_dsr != NULL || !count) {
					if (temp_dsr->newflight.F_name==tname) {
						cout << "The flights details are following: " << endl;
						cout << "Flight name: " << temp_dsr->newflight.F_name << endl;
						cout << "Flight source: " << temp_dsr->newflight.source << endl;
						cout << "Flight destination: " << temp_dsr->newflight.dest << endl;
						cout << "Flight arrival time: " << temp_dsr->newflight.arrtime << endl;
						cout << "Flight dept time: " << temp_dsr->newflight.depttime << endl;
						cout << "Update Flight Status to landed: ";  temp_dsr->newflight.status = "Landed";
						pushtostack(temp_dsr->newflight.F_name, temp_dsr->newflight.source, temp_dsr->newflight.dest, temp_dsr->newflight.arrtime, temp_dsr->newflight.depttime, temp_dsr->newflight.status);

						count++;
					}//if
					else temp_dsr=temp_dsr->dos_arr_next;
				}//while

			}//elseif
		}//else
		if (count == 0)
			cout << "Flight not found.." << endl;
		int tttt;
		cout << "Do you want to perform another operation(Y/1:N/0):"; cin >> tttt;
		return tttt;
	}//fun

int alreadylanded() {
	flight temp;
	 temp=head->newflight;
	 stack* temps;
	cout << "The flights which are already landed are: " << endl;
	
	while (head != NULL) {
		cout << "Flights details are as follow: " << endl;
		cout<<"Flight name: " <<head->newflight.F_name << endl;
		cout<<"Flight source: " <<head->newflight.source << endl;
		cout<<"Flight Destination: " <<head->newflight.dest << endl;
		cout<<"Flight arrival time: " <<head->newflight.arrtime << endl;
		cout<<"Flight Departure time: " <<head->newflight.depttime << endl;
		cout<<"Flight status: " <<head->newflight.status << endl;
		cout<<"-----------------details done-------------------" << endl;
		temps = head;
		head = head->next;
		delete temps;
	}
	system("cls");
	int tttt;
	cout << "Do you want to Perform another function:(Y:1/N:0) "; cin >> tttt;
	return tttt; }
int remove() { return 0; }
void pushtostack(string tF_name, string tsource, string tdest, string tarrtime, string tdepttime, string tstatus){
	flight temp;
	temp.F_name = tF_name;
	temp.source=tsource;
	temp.dest=tdest;
	temp.arrtime=tarrtime;
	temp.depttime=tdepttime;
	temp.status=tstatus;
	stack* list = new stack;
	
	if (head == NULL) {
		list->newflight = temp;
		head = list;
		head->next = NULL;
	}
	else {
		head->next->newflight = temp;
		head=head->next;
	}
} 
