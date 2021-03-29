#include <iostream>
  
using namespace std;

const int  m=50;

class ITEMS

{

    int itemcode[m];
    
    float itemPrice[m];
    
    int count;
    
    public :
    
    void CNT(void)
    
    {
    
        count=0;
        
    }
    
    void getitem(void);
    
    void displaySum(void);
    
    void remove(void);
    
    void displayItems(void);
    
};

void ITEMS :: getitem(void)

{

    cout<<"Enter item code:";
    
    cin>>itemcode[count];
    
    cout<<"Enter item cost:";
    
    cin>>itemPrice[count];
    
    count++;
    
}

void ITEMS::displaySum(void)

{

    float sum=0;
    
    for(int i=0;i<count;i++)
    
            sum=sum+itemPrice[i];
            
            cout<<"\n Total value:"<<sum<<"\n";
            
}

void ITEMS ::remove(void)

{

    int a;
    
    cout<<"enter item code";
    
    cin>>a;
    
    for(int i=0;i<count;i++)
    
        if(itemcode[i]==a)
        
            itemPrice[i]=0;
            
}

void ITEMS :: displayItems(void)

{
    cout<<"\n code      price\n";
    
    for(int i=0;i<count;i++)
    
    {
    
    
        cout<<"\n"<<itemcode[i];
        
        cout<<"   "<<itemPrice[i];
        
    }
    
    cout<<"\n";
    
}

int main()

{

    ITEMS order;
    
    order.CNT();
    
    int x;
    
    do
    
    {
    
        cout<<"\nYou can do the following";
        
        cout<<"Enter appropriate number\n";
        
        cout<<"\n 1: Add an item";
        
        cout<<"\n 2: Display total value";
        
        cout<<"\n 3 Delete an item";
        
        cout<<"\n 4 Display all items";
        
        cout<<"\n 5: Quit";
        
        cout<<"\n What option do you pick?";
        
        cin>>x;
        
        switch (x)
        
        {
        
            case 1:order.getitem();
            
            break;
            
            case 2: order.displaySum();
            
            break;
            
            case 3:order.remove();
            
            break;
            
            case 4:order.displayItems();
            
            break;
            
            case 5:break;
            
            default:cout<<"Error in input: try again\n";
            
        }
        
    }
    
    while(x!=5);
    
    return 0;
}
