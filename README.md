#include <iostream>
#include <cstdlib>
using namespace std;
class ATM
{
protected:
    int pass, adhaar, mob, bal, acno;
    string name, acc_type, pan, email;

public:
    void open(int x = 0)
    {
        int y = x;
        cout << "to open a new account\nplease enter your name\n";
        cin >> name;
        cout << "please enter your mobile no\n";
        cin >> mob;
        cout << "please enter your email address\n";
        cin >> email;
        cout << "please enter your pan no\n";
        cin >> pan;
        cout << "please enter your aadhar no\n";
        cin >> adhaar;
        cout << "please enter your account type\n";
        cin >> acc_type;
        acno = rand();
        cout << "your accout no is " << acno << '\n';
        cout << "enter the amount you want to deposit\n";
        cin >> bal;
        cout << "please enter your 4 digit ATM pin\n";
        cin >> pass;
        cout << "your ATM card will be delivered soon as per your aadhaar's address\n";
        cout << "thankyou for banking with us\n";
        if (y == 1)
        {
            display();
        }
    }
    void display()
    {
        cout << "hello " << name << " you are our precious costmer\nyou have a " << acc_type << " accout\nyour account number is " << acno << "\nyour account balance is " << bal << "\nfor more information please visit the nearest branch\nthankyou for banking with us\n";
    }
    void deposit()
    {
        int x;
        cout << "welcome " << name << "\nplease enter the amount to deposit\n ";
        cin >> x;
        bal = bal + x;
        cout << "total amount in the accout is " << bal << "\nthankyou for banking with us\n";
    }
    void withdraw()
    {
        int x;
        cout << "welcome " << name << "\nplease enter the amount to withdraw\n";
        cin >> x;
        if (x > bal)
            cout << "insufficient balance\nthankyou for banking with us\n";
        else
        {
            bal = bal - x;
            cout << "total amount remaining in the account is " << bal << "\nthankyou for banking with us\n";
        }
    }
    void inq()
    {
        cout << "welcome " << name << "\nyour total account balance is " << bal << "thankyou for banking with us\n";
    }
    void atm()
    {
        cout << "please visit the branch for the new ATM card\nthankyou for banking with us\n";
    }
    void chpin()
    {
        cout << "please enter your new 4 digit pin\n";
        cin >> pass;
        cout << "your pin has been successfully changed\nthankyou for banking with us\n";
    }
    int enter(int p)
    {
        int x = p;
        if (x == pass)
        {
            return 1;
        }
        else
            return 0;
    }
};
int main()
{
    ATM a;
    int x, p;
    cout << "welcome to the bank\n";
    cout << "please press 1 if you inserted the card else press any other key\n";
    cin >> x;
    if (x == 1)
    {
        int y, q;
        cout << "please enter your 4 digit pin\n";
        cin >> p;
        cout << "please press\n1 for account details\n2 for cash deposit\n3 for withdraw\n4 for balance inqury\n5 for change the pin\n";
        cin >> y;
        switch (y)
        {
        case 1:
            q = a.enter(p);
            if (q == 1)
            {
                a.open(y);
            }
            else
                cout << "incorrect pin please try again\n";
            break;
        case 2:
            q = a.enter(p);
            if (q == 1)
            {
                a.deposit();
            }
            else
                cout << "incorrect pin please try again\n";
            break;
        case 3:
            q = a.enter(p);
            if (q == 1)
            {
                a.withdraw();
            }
            else
                cout << "incorrect pin please try again\n";
            break;
        case 4:
            q = a.enter(p);
            if (q == 1)
            {
                a.inq();
            }
            else
                cout << "incorrect pin please try again\n";
            break;
        case 5:
            q = a.enter(p);
            if (q == 1)
            {
                a.chpin();
            }
            else
                cout << "incorrect pin please try again\n";
            break;
        }
    }
    else
    {
        cout << "please enter\n1 for open new account\n2 for apply a new ATM card\n";
        int z;
        cin >> z;
        switch (z)
        {
        case 1:
            a.open();
            break;
        case 2:
            a.atm();
            break;
        }
    }
    return 0;
}
