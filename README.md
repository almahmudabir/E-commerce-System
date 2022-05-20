# E-commerce-System
//E-Commerce Management System
#include<iostream>
#include<string.h>
using namespace std;
int t=0;
class reg
{
    string  v;
    public:
    int num;
    string name,add;

        void R()
        {
                cout<<"Please complete your registration........"<<endl;
                cout<<"Name:";
                cin>>name;
                cout<<"Number: ";
                cin>>num;
                cout<<"Address: ";
                cin>>add;
        }
 void set(string v1)
    {
         v=v1;
    }

    friend void get(reg   r);//Friend Function declaration
};
 void get(reg   r)//Function Argument
{
    r.v;
    cout<<r.v;
}
class C : public reg //SIngle Inheritance
{
public:
    void D()
    {
        cout<<"***** Registration Done *****"<<endl;

    }
};

class product
{
    public:
        int p,quan=1;
        void P()
        {

                cout<<"\nPlease select your product: "<<endl;
                cout<<"1. Mobile "<<"\n"<<"2. Laptop "<<"\n"<<"3. LED T.V "<<"\n"<<"4. Samsung Refrigerator"<<"\n"<<"5. Tablet "<<"\n";
                cout<<"Enter Your Product Number: ";
                cin>>p;
                switch(p)
                {
                    case 1: {
                                        cout<<"1. Mobile: 50000"<<endl;
                                        cout<<"Quantity: ";
                                        cin>>quan;
                                        t=50000*quan;
                                        cout<<"\nTotal Bill: "<<t<<endl;
                                        break;
                                  }
                     case 2: {
                                        cout<<"2. Laptop: 120000"<<endl;
                                        cout<<"Quantity: ";
                                        cin>>quan;
                                        t=120000*quan;
                                        cout<<"\nTotal Bill: "<<t<<endl;
                                        break;
                                    }
                     case 3: {
                                        cout<<"3. LED T.V: 20000"<<endl;
                                        cout<<"Quantity: ";
                                        cin>>quan;
                                        t=20000*quan;
                                        cout<<"\nTotal Bill: "<<t<<endl;
                                        break;
                                    }
                     case 4: {
                                        cout<<"4. Samsung Refrigerator: 150000"<<endl;
                                        cout<<"Quantity: ";
                                        cin>>quan;
                                        t=150000*quan;
                                        cout<<"\nTotal Bill: "<<t<<endl;
                                        break;
                                  }
                     case 5: {
                                        cout<<"5. Tablet: 100000"<<endl;
                                        cout<<"Quantity: ";
                                        cin>>quan;
                                        t=100000*quan;
                                        cout<<"\nTotal Bill: "<<t<<endl;
                                        break;

                                    }
                    default: cout << "\nError! "<<endl;
                                        break;


                }
        }

};

class payment
{
    public:
         int q;
        void Y()//total bill
        {
            cout<<"\n Confirm your order and pay the bill. \n \n"<<"Your Total Bill is: "<<t<<"\n \n"<<"You can pay with: \n"<<"1. Bkash" <<"\n" <<"2. Rocket"<< "\n"<< "3. Nogod"<< "\n"<<" 4.Visa or Mastercard"<<" \n"<<"5.Cash on Delivery (COD)  \n";
            cout<<"Enter Your Payment Method: ";
            cin>>q;
            switch(q)
                {
                    case 1: cout<<"\n1. You have chose Bkash\n"<<endl;
                                        break;
                     case 2: cout<<"\n2. You have chose Rocket\n"<<endl;
                                        break;
                     case 3: cout<<"\nYou have chose Nogod\n"<<endl;
                                        break;
                     case 4: cout<<"\nYou have chose Visa or Mastercard\n"<<endl;
                                        break;
                     case 5: cout<<"\nYou have chose COD\n"<<endl;
                                        break;
                    default:cout << "\nError! \n"<<endl;
                                        break;

                }

        }

};

class confirm
{
    public:

        void E()
        {
            cout<<"Confirm Your Order.";

        }
};
class confirm_2 : public confirm //Hierarchical Inheritance
{
    public:

        void E()
        {
            cout<<"\nYour Total Bill is: "<<t<<"\n";     //Total bill
        }
};

class confirm_3 : public confirm //Hierarchical Inheritance
{
    public:
        void E()
        {
            cout<<"We have received your order successfully.\n";
        }
};

int main()
{
    reg o8;
    o8.set("\n---------------Welcome to our E-commerce site------------------------------\n");
    get(o8);
    C o1,o2[3];    //Object=o
    o1.R();
     for (int i=0; i<=2;i++)//Array  in  objects
    {
        o2[i].D();
    }
    product o3;
    o3.P();
    payment o4;
    o4.Y();
    confirm o5; //polymorphism
    o5.E();
    confirm_2  o6; //polymorphism
    o6.E();
    confirm_3 o7; //polymorphism
    o7.E();
    return 0;
}
