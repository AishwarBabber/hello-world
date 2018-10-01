	#include<iostream>
	#include <ostream>
	#include <iomanip>
	using namespace std;
	
	int f=0;
	
	class a
	
	{
				 
	public:
		
		int seat=100,t,p[100]={0},k=0,yo=0, cost=0,s=1;
	 
	  
	  void show_details();
	
	  void bookticket();
	
	  void show();
	
	  void inScreen();
	
	  void calCost(int i);
	  
	  void seatsAvailable();
	  
	  //void seatDisplay(int m);
	  
	  void showTime();
	  
	  void seatsAvailable(int i);
	  
	  void seatDisplay();
	  
	  /*a(int seatnum)
	  {
	  	//cout<<"Enter seat number"
	  	
		m=seatnum;
	  }*/
	  
	
		  

	
	} movie[5];
	
	 void a::seatDisplay()
{	int choice;
	 s=1;
	
	for(int i=0;i<10;i++)
	{
		
		for(int j=0;j<=9;j++)
		{
			yo=0;

			if( j==2 || j==8) 
			
				cout<<"\t";
						
			for(int x=0;x<k;x++)
		   	{
				if(p[x]==(s+yo)) 
				{

				cout<<"--  ";
				if(j==7 || j==1)
				cout<<"\t";
				yo++;
				j++;
				} 
				
			} 

												
				if(s<10)
				cout<<setw(2)<<setfill('0');
				s=s+yo;
				if(j==10) 
				
				continue;
				else
				cout<<s<<"  " ;			 
				s++;
	}
		 
	    if(i==2|| i==7 )
			cout<<"\n";
		
		cout<<endl;
	}
	
	cout<<"\n----------------SCREEN THIS SIDE------------------"<<endl;

 	while(1)
		{
		cout<<"\nEnter the seat number to book your ticket"
		<<"\nor \nEnter 0 to confirm\n";
		cin>>t;
		cout<<endl<<endl;
		
		if(t==0) 
		{
		calCost(k);
		k=0;
		cout<<"1. Go Back To Main Menue"
		<<endl<<"2.Exit\n";
		cin>>choice;
		cout<<endl<<endl;
		if(choice==2)
		exit(0);
		else 
		inScreen();
	
		}
		
		else {
		
		p[k++]=t;
		seatDisplay();  }

		}
	}
	
	void a:: calCost(int i)
	{
		int c=0;
		for(int i=0;i<100;i++)
		{
			if(p[i]<=30 && p[i]>=1) {
			c++;
			cost= cost+((c)*300);
			c=0;
		}
			else if(p[i]>=31 && p[i]<=80){
			c++;
			cost = cost + ((c)*200);
			c=0;
			}
			
			else if(p[i]>=81 && p[i]<=100)
			{ c++;
			  cost = cost + ((c)*150);
			  c=0;
			}
//			else {
//			cout<<"Seat No. Not Valid\n\n";
//			}
		}
			cout<<"\n Total Price = "<<cost<<endl<<endl;
			cost=0;
		}
	
	
//	void a::showTime(int m)
//	{
//		
//		cout<<"\n\n\t\t\t1.Time \n\t\t\t"
//	
//	  <<"2.Time \n\t\t\t"
//	
//	  <<"3.Time \n\t\t\t"
//	  
//	  <<"4.Time \n\t\t\t"
//	  
//	  <<"5.Time \n\t\t\t";
//	
//	  cout<<"\n\t\t\tEnter movie time:->\t";
//	
//	  cin>>t;
//	  seatsAvailable(t);
//		
//	}
	
//	void a:: seatsAvailable(int i)
//	{
//	//	int i;
//		cout<<"\	Available Seat at ";
//	//	movie[i]
//		if(i<=2)
//		cout<<i<<" AM\n"<<endl;
//		else if(i>2 && i<=5)
//		cout<<i<<" PM\n"<<endl;
//		else 
//		cout<<"Show not available at this time";	
//		seatDisplay();
//		
//	}
	
	
	
	void a::bookticket()
	{
		int m;
		cout<<"\n\n\t\t\t1.Movie 1\n\t\t\t"
	
	  <<"2.Movie 2\n\t\t\t"
	
	  <<"3.Movie 3\n\t\t\t"
	  
	  <<"4.Movie 4\n\t\t\t"
	  
	  <<"5.Movie 5\n\t\t\t";
	
	  cout<<"\n\t\t\tEnter movie choice:-> ";
	
	  cin>>m;
	  f=m;
	  	seatDisplay();
	  
	 // showTime(m);
	  
//	  if(c==1)
//		inScreen();
//		else if(c==2)
//		showTime();
		
	  
//	   seatsAvailable(m);
	  	
	}
	
	void a::inScreen()
	{
			int w=0;
	
		
	  cout<<"\t\t\t1.Running Shows\n\t\t\t"
	
	  <<"2.Book Tickets\n\t\t\t"
	
	  <<"3.Exit \n\t\t\t";
	
	  cout<<"\n\t\t\tEnter your choice:-> ";
	
	  cin>>w;
	  
	  switch(w)
	
	  {
	
	    case 1:  show_details();
	
	      break;
	      
	    case 2:  bookticket();
	
	      break;
	
	    case 3:  exit(0);
	
	  }
	  
	}
	
	void a::show_details()
	
	{
		int c;
		cout<<"\tMovie 1\n"
		<<"\tMovie 2\n"
		<<"\tMovie 3\n"
		<<"\tMovie 4\n"
		<<"\tMovie 5\n";
		
		cout<<"\n\n\t1.Back\n"
		<<"\t2.Book tickets";
		
		cin>>c;
		
		if(c==1)
		inScreen();
		else if(c==2)
		bookticket();
	
	}
	
	
	
	int main()
	 {
	 	a o;
	 	o.inScreen();
	 
	
	
	  
	   return 0;
	}
