# hello-world
Final Project
//Program Name: Run of Terror
//Authors: Cristian, Djamel, Gift.
//Last modified:09/23/21
//Purpose:

#include <iostream>
#include <string>
#include <vector>
using namespace std;

class Thief//class named thief
{
  public: //Access Specifier
  int Health = 100,Attack1_1 = 100;

    virtual void setHealth(int x)//virtual function sethealth.
 {
   Health = Health - x;
 }
    [[nodiscard]] virtual int getHealth() const//virtual function for gethealth.
 {
   return Health;
 }
};


class Innocent :public Thief
{
public: //Access Specifier
int kick =10, punch = 20, headbutt = 5;
int Health = 100;
 void setHealth(int x) override
 {
   Health = Health - x;
 }
 [[nodiscard]] int getHealth() const override
 {
   return Health;
 }
};

class Error
{ 
  string errormessage;

  public:
  Error(string msgfrommain)
  {
    errormessage=msgfrommain;
  }
  string what()
  {
    return errormessage;
  }

};
int main()
{
try{
    vector<string> items;
    int fight, decision;
    string ItemName, pick;
    Thief thief;
    Innocent innocent;
    

            cout << "You will be playing a game which you have to survive from the killer. You have to select the right decisions to escape" << endl;
            cout << "If you select the wrong option you might not survive and die. Ready set go." << endl;
            cout<<endl;

            cout << "Scene: You have just arrived from work you lock your car and approach your front door. You notice that there is a window broken" << endl;
            cout << "so you open the door and see there is a thief inside your home, the thief see you." << endl;
            cout << endl;

            cout << "Enter '1' to run off to your car or '2' to fight the thief " << endl;
            cin >> decision;

            if (decision==1||decision==2)
            {
              decision=decision;
            }
            else
            {
              throw Error("You have entered a invalid answer");
            }
    if(decision==1)
        {
      int decision2;
            cout << "You have decided to run." << endl;
            cout << endl;

            cout << "You will need to make a decision. You are able to take 3 items with you before you leave." << endl;
            cout << endl;

    for (int i=0 ; i < 3; i++)
        {
            cout << "Enter item number " << i + 1 << ":" << endl;
            cin >> ItemName;
            items.push_back(ItemName);
        }
            cout << endl;
            cout << "YOU DROPPED SOMETHING!!!!" << endl;
            cout << "There is no way you can go back to pick it up, the thief will kill you " << endl;
            items.pop_back();
            cout << "right now you have: " << items.size() << "items" << endl;
    for (auto & item : items)
        {
            cout << item << endl;
        }
            cout << "JUST KEEP RUNNING!!!!!!!!!!!!" << endl;

            cout << endl;
            cout << "You have the option to run towards your car or your neighbors house" << endl;
            cout << "HURRY!!!, MAKE A DECISION RIGHT NOW!!!" << endl;
            cout << "Pick '1' to run to your car and '2' to your neighbors " << endl;
            cin  >> decision2;

            if (decision2==1||decision2==2)
            {
              decision=decision;
            }
            else
            {
              throw Error("You have entered a invalid answer");
            }

    if (decision2 == 1)
        {
            cout << "You decided to run towards your car.You are able to escape and run away."<<endl;
            cout << "YOU WON!!!!!!!"<<endl;
            cout << "GAME OVER............."<<endl;
        }
    if (decision2 ==2)
        {
            cout << "run as fast as you can to your neighbours house" << endl;
            cout << "knock, knock, knock............." << endl;
            cout << "knock, knock, knock............." << endl;
            cout << "there is no response, hit the door" << endl;
            cout << "bam, bam, bam, bam...." << endl;
            cout << "Neighbor: go away we can't risk our lives for you " << endl;

            cout << endl;
            cout << "You need to do something the thief is approaching " << endl;
            cout << endl;

            int decision3;
            cout << "Time is running out. Select '1' to break into the house or '2' to fight the thief. " << endl;
            cin >> decision3;

            if (decision3==1||decision3==2)
            {
              decision=decision;
            }
            else
            {
              throw Error("You have entered a invalid answer");
            }

             try
                {
    if (decision3==1)
        {
             cout << "You have decided to break into the house.The neighbors finally calls the cop and the thief runs away" << endl;
             cout << "You have won the game because the thief was afraid." << endl;
             cout << "GAME OVER!!!" << endl;
        }
    else
        {
             cout << "You have decided to fight" << endl;
             //only the thief will be able to make an attack here and the user will end up getting killed
             innocent.setHealth(thief.Attack1_1);
    if(innocent.getHealth() <= 0)
        {
             throw  (decision3);
        }
        }
                 }
             catch(...)
                {
             cout << "You have died. Sorry maybe next time.GAME OVER....." << endl;
                }
        }
        }
   if (decision == 2)
        {
             cout << "You've decide to fight." << endl;
             cout << "Your health right now is: " << innocent.getHealth() << '\n' << endl;
             cout << "The killers health right now is: " << thief.getHealth() << '\n' << endl;

             cout << "You have to make a surprise attack and you better be wise about it" << endl;
             cout << "You have five moves to end this thief or else he'll be the one to end you" << endl;
             cout << "Enter #1 to Kick, #2 to Punch, and 3 to Headbutt the thief." << endl;
             cout<<endl;

   for (int i = 0; i <= 5; i++)
        {
// cout << "This is mr i" << i << endl;
   if(thief.getHealth() <= 0)
        {
            cout << "You Survived! " << endl;
        }
   else if (thief.getHealth() > 0 && i==5 )
        {
          cout<<"********************************"<<endl;
          cout<<endl;
          cout<<"Thief: You should have killed me while you had the chance"<<endl;
          cout<<endl;
          cout<<"User:PLEASE NO DON'T KILL ME!!!!"<<endl;
          cout<<endl;
          cout<<"Theif:(Thief takes off mask which ends up being their bestfriend)Sorry since you saw my face this means I have to end you."<<endl;
           innocent.setHealth(thief.Attack1_1);
            cout << "Health of innocent status is: " << innocent.getHealth() << endl;
            
            cout<<endl;
            cout<<"You died, GAME OVER!!!"<<endl;
        }
   else
        {
            cout << "Keep Fighting, don't stop till The Killer Dies! " << endl;
            cin  >> fight;
            if (fight==1||fight==2||fight==3)
            {
              fight=fight;
            }
            else
            {
              throw Error("You have entered a invalid answer");
            }

   if (fight == 1)
        {
            thief.setHealth(innocent.kick);
            cout << "Health of thief status is: " << thief.getHealth() << endl;

        }
   if (fight == 2)
        {
            thief.setHealth(innocent.punch);
            cout << "Health of thief status is: " << thief.getHealth() << endl;
        }
   if (fight == 3 )
        {
            thief.setHealth(innocent.headbutt);
            cout << "Health of thief status is: " << thief.getHealth() << endl;
        }
       }
      }
     }
   }

    catch(Error message)
      {
        cout<<"Error: "<<message.what();
      }return 0;
}
