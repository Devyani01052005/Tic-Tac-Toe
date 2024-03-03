//# Tic-Tac-Toe



#include <iostream>
using namespace std;

    char a[3][3]={{'1','2','3'},{'4','5','6'},{'7','8','9'}};
    char turn='X';
    int row,column;
    bool draw=false;


void display(){
   
    // system("cls");
    
        cout<<"\n\n\tTIC TAC TOE "<<endl;
        cout<<"\t      - by Devyani\n\n"<<endl;
    
        cout<<"     player1 [X]\n     player2 [0]\n"<<endl;
    
        cout<<"\t      |     |     "<<endl;
        cout<<"\t   "<<a[0][0]<<"  |  "<<a[0][1]<<"  |  "<<a[0][2]<<"  "<<endl;
        cout<<"\t _____|_____|_____"<<endl;
    
        cout<<"\t      |     |     "<<endl;
        cout<<"\t   "<<a[1][0]<<"  |  "<<a[1][1]<<"  |  "<<a[1][2]<<"  "<<endl;
        cout<<"\t _____|_____|_____"<<endl;
    
        cout<<"\t      |     |     "<<endl;
        cout<<"\t   "<<a[2][0]<<"  |  "<<a[2][1]<<"  |  "<<a[2][2]<<"  "<<endl;
        cout<<"\t      |     |     "<<endl;
}

    void player_turn(){
    
        int choice;
   
        if(turn=='X')
        {
            cout<<"\n\tplayer1 [X] turn:"<<endl;
        }
    
        if(turn=='0')
        {
            cout<<"\n\tplayer2 [0] turn:"<<endl;
        }
    
        cin>>choice;
        
    switch(choice){
        
        case 1:
               row=0;column=0;
               break;
        
        case 2:
               row=0;column=1;
               break;
        
        case 3:
               row=0;column=2;
               break;
        
        case 4:
               row=1;column=0;
               break;
        
        case 5:
               row=1;column=1;
               break;
        
        case 6:
               row=1;column=2;
               break;
        
        case 7:
               row=2;column=0;
               break;
        
        case 8:
               row=2;column=1;
               break;
        
        case 9:
               row=2;column=2;
               break;
               
        default:
               cout<<"INValid choice"<<endl;
                break;
        }
    
            if(turn == 'X' && a[row][column]!='X' && a[row][column]!='0')
            {
                a[row][column]='X';
                turn='0';
            }
            else if(turn == '0' && a[row][column]!='X' && a[row][column]!='0')
            {
                a[row][column]='0';
                turn='X';
            }
            else
            {
                cout<<"box is already filled!!\n please try again\n"<<endl;
                player_turn();
            }
       
         display();
}    

    bool gameover(){
    
        //check win
        for(int i=0;i<3;i++)
        if(a[i][0]==a[i][1] && a[i][0]==a[i][2] || a[0][i]==a[1][i] && a[0][i]==a[2][i])
        return false;
        
        if(a[0][0]==a[1][1] && a[0][0]==a[2][2] || a[0][2]==a[1][1] && a[0][2]==a[2][0])
        return false;
        
        //if there is any box not filled yet!!
        for(int i=0;i<3;i++)
        for(int j=0;j<3;j++)
        
        if(a[i][j]!='X'&& a[i][j]!='0' )
        return true;
        
        //draw
        draw=true;
        return false;
}
   
int main(){
    
    while(gameover())
    {
        display();
       // system("cls");
        player_turn();
        system("cls");
        gameover();
    } 
  
        if(turn=='X' && draw==false)
        cout<<"\n\n\tplayer2 [0] wins!!\n\n    CONGRATULATIONS"<<endl;
    
        else if(turn=='0' && draw==false)
        cout<<"\n\n\tplayer1 [X] wins!!\n\n    CONGRATULATIONS"<<endl;
    
        else
        cout<<"    GAME DRAW!!"<<endl;
    
       
    return 0;  
    
}








