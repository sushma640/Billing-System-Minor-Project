# Billing-System-Minor-Project
#include<iostream>
using namespace std;

int returnBill(){
    char c;
    char item;
    char vegItem;
    char nonvegItem;
    int billAmount;
    char selectAgain;
    cout<<"---------------------Welcome to online Food Order-------------------------"<<endl;
    cout<<"---------------------Please follow below instructions----------------------"<<endl;
    cout<<"Step 1 : Please press s to start your order"<<endl;
    cout<<"Step 2 : You can order bothveg and non-veg item"<<endl;
    cout<<"Step 3 : Please press a to select veg item"<<endl;
    cout<<"Step 4 : Please press b to select non-veg item"<<endl;
    cout<<"Step 5 : You will get your final Bill after your order"<<endl;
    start:
    cin>>c;
    if(c=='s'||c=='S'){
        items:
        cout<<"Please select your choice"<<endl;
        cout<<"(a)Veg                (b)Non-Veg"<<endl;
        cin>>item;
        if(item=='a' || item=='A'){
            vegItemList:
            cout<<"Please select 1,2,3,4,5 as per your choice"<<endl;
            cout<<"(1)Paneer  : Price:-250/-"<<endl;
            cout<<"(2)Burger  : Price:-50/-"<<endl;
            cout<<"(3)Pizza  : Price:-100/-"<<endl;
            cout<<"(4)choumin  : Price:-150/-"<<endl;
            cout<<"(1)veg-Roll  : Price:-100/-"<<endl;
            
            cin>>vegItem;
            if(vegItem=='1'){
                billAmount=billAmount+250;
            }else if(vegItem=='2'){
                billAmount+=50;
            }else if(vegItem=='3'){
                billAmount+=100;
            }else if(vegItem=='4'){
                billAmount+=150;
            }else if(vegItem=='5'){
                billAmount+=100;
            }else{
                cout<<"You have entered wrong value, please try again!"<<endl;
                goto vegItemList;

            }
            cout<<"Do you want to add more items , y or n ?"<<endl;
            cin>>selectAgain;
            if(selectAgain=='y'){
                goto items;
            }else{
                return billAmount;
            }

        }else if(item=='b' || item=='B'){
            nonvegItemList:
            cout<<"Please select 1,2,3,4,5 as per your choice"<<endl;
            cout<<"(1)Chicken  : Price:-350/-"<<endl;
            cout<<"(2)Chicken Burger  : Price:-100/-"<<endl;
            cout<<"(3)Chicken Pizza  : Price:-200/-"<<endl;
            cout<<"(4)Non-veg choumin  : Price:-200/-"<<endl;
            cout<<"(1)Non-veg-Roll  : Price:-200/-"<<endl;
            
            cin>>nonvegItem;
            if(nonvegItem=='1'){
                billAmount=billAmount+350;
            }else if(nonvegItem=='2'){
                billAmount+=100;
            }else if(nonvegItem=='3'){
                billAmount+=200;
            }else if(nonvegItem=='4'){
                billAmount+=200;
            }else if(nonvegItem=='5'){
                billAmount+=200;
            }else{
                cout<<"You have entered wrong value, please try again!"<<endl;
                goto nonvegItemList;

            }
            cout<<"Do you want to add more items , y or n ?"<<endl;
            cin>>selectAgain;
            if(selectAgain=='y'){
                goto items;
            }else{
                return billAmount;
            }

        }else{
            cout<<"You have entered wrong value, please try again!"<<endl;
            goto items;
        }



    }else{
        cout<<"You have entered wrong value,please press s!"<<endl;
        goto start;
    }

    return billAmount;


}

int main(){
    int returnBill(void);
    int total_amount=returnBill();
    cout<<"Your total Bill Amount is "<<total_amount<<endl;
    cout<<"Thankyou for your order ! "<<endl;

    return 0;
}
