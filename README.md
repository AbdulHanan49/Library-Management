# Library-Management
#include<iostream>
#include<string>
#include<fstream>
using namespace std;


void Collecting_Data( string book[100],string type [100],string author[100],int &i,int &j, int &k,int &cont,string File_Name){

    ofstream file;
    file.open(File_Name);

cout<<" How many books you want to enter : ";
    int n=0;
    cin>>n;
    cont=n;
    cin.ignore();


    while(n!=0){

cout<<endl;
        cout<<" Enter the name of book : ";
         //cin>>book[i];
         getline(cin,book[i]);
         file<<book[i]<<endl;
        cout<<" Enter the type of book : ";
         //cin>>type[j];
         getline(cin,type[j]);
         file<<type[i]<<endl;
        cout<<" Enter the author of book : ";
        //cin>>author[k];
        getline(cin,author[k]);
        file<<author[i]<<endl;
        cout<<endl<<endl;
        file<<endl<<endl;

        i++;
        j++;
        k++;
        n--;

    }

  cout<<"||******************************|| THANK YOU FOR ENTERING THE DATA ||********************************||"<<endl;

}

void Menue1( ){


 cout<<"||----------------------------------------|| MENUE ||-----------------------------------------------||"<<endl;
 cout<<"||                                                                                                  ||"<<endl;
 cout<<"|| 1. Librarian.                                                                                    ||"<<endl;
 cout<<"|| 2. Sign Up(USER)                                                                                       ||"<<endl;
 cout<<"|| 3. Exit.                                                                                         ||"<<endl;
 cout<<"||--------------------------------------------------------------------------------------------------||"<<endl;

}

void Liabrary_Menue( ){

 cout<<"||----------------------------------------|| MENUE ||-----------------------------------------------||"<<endl;
 cout<<"||                                                                                                  ||"<<endl;
 cout<<"|| 1. Add.                                                                                          ||"<<endl;
 cout<<"|| 2. Remove .                                                                                      ||"<<endl;
 cout<<"|| 3. Edit.                                                                                         ||"<<endl;
 cout<<"|| 4. Exit.                                                                                         ||"<<endl;
 cout<<"||--------------------------------------------------------------------------------------------------||"<<endl;

}

void Menue2( ){


 cout<<"||----------------------------------------|| MENUE ||-----------------------------------------------||"<<endl;
 cout<<"||                                                                                                  ||"<<endl;
 cout<<"|| 1. Issue of Book                                                                                 ||"<<endl;
 cout<<"|| 2. Return of Book                                                                                ||"<<endl;
 cout<<"|| 3. Exit.                                                                                         ||"<<endl;
 cout<<"||--------------------------------------------------------------------------------------------------||"<<endl;



}

void ADD(string book[100],string type[100],string author[100],int &i,int &j,int &k,int &count,string File_Name){

    ofstream file(File_Name,ios::app);

 cout<<" How many books you want to enter (eg 1,2,3...etc) : ";
    int N=0;
    cin>>N;
     cin.ignore();



    while(N!=0){

cout<<endl;
file<<endl;
        cout<<" Enter the name of book : ";
         //cin>>book[i];
         getline(cin,book[i]);
         file<<book[i]<<endl;
        cout<<" Enter the type of book : ";
         //cin>>type[j];
         getline(cin,type[j]);
         file<<type[j]<<endl;
        cout<<" Enter the author of book : ";
        //cin>>author[k];
        getline(cin,author[k]);
        file<<author[k]<<endl;
        cout<<endl<<endl;
        file<<endl<<endl;
        //file<<endl<<endl;

        i++;
        j++;
        k++;
        N--;
        count++;

    }

}

void Remove_Book(string book[100],string type[100],string author[100],int count ,int cont,string File_Name,int &L){


    L=cont+count;
    ofstream file(File_Name);

    cout<<" Following are the books we have : ";

    for(int i=0,j=0,k=0;i<L;i++,j++,k++){
            cout<<endl;
        cout<<"Book"<<i+1<<endl;
        cout<<"    Name : "<<book[i]<<endl;
        cout<<"    Type : "<<type[j]<<endl;
        cout<<"    Author : "<<author[k]<<endl;
           cout<<endl;
    }

    cout<<" Enter the number of book you want to Remove (eg 1,2,3,.. etc) : ";
    int Book_No;
    cin>>Book_No;

    int num=0;
    num=Book_No-1;
    book[num]="Book Removed";
    //file<<book[num]<<endl;
    type[num]="Book Removed";
    //file<<type[num]<<endl;
    author[num]="Book Removed";
    //file<<author[num]<<endl;


    for(int i=0;i<L;i++){
            file<<endl;
        file<<book[i]<<endl;
        file<<type[i]<<endl;
        file<<author[i]<<endl;
          file<<endl<<endl;

    }

}

void Edit_Book(string book[100],string type[100],string author[100],int count ,int cont,string File_Name ){

  int L=0;
    L=cont+count;

    ofstream file(File_Name);

    cout<<" Following are the books we have : ";

    for(int i=0,j=0,k=0;i<L;i++,j++,k++){
            cout<<endl;
        cout<<"Book"<<i+1<<endl;
        cout<<"    Name : "<<book[i]<<endl;
        cout<<"    Type : "<<type[j]<<endl;
        cout<<"    Author : "<<author[k]<<endl;
           cout<<endl;
    }

    cout<<" Enter the number of book you want to Edit (eg 1,2,3,.. etc) : ";
    int Book_No;
    cin>>Book_No;

cin.ignore( );
    int num=0;
    num=Book_No-1;
    cout<<" Enter the name of book :";
    string name;
    getline(cin,name);
    book[num]=name;
   // file<<book[num]<<endl;
    cout<<" Enter the type of the book : ";
    string T;
    getline(cin,T);
    type[num]=T;
    //file<<type[num]<<endl;
    cout<<" Enter the author of the book : ";
    string auth;
    getline(cin,auth);
    author[num]=auth;
    //file<<author[num]<<endl;


    for(int i=0;i<L;i++){
        file<<endl;
       file<<book[i]<<endl;
       file<<type[i]<<endl;
       file<<author[i]<<endl;
        file<<endl<<endl;

    }




}
void Sign_Up(string N_Name ){

    cin.ignore( );
    string New_Name;
    string Password;
    cout<<" Enter your Name : ";
    getline(cin,New_Name);

    cout<<" Enter your Password : ";
    getline(cin,Password);

    cout<<"||*******************|| CONGRATULATION YOUR ACCOUNT HAS BEEN CREATED ||**********************||"<<endl;

    cout<<" Enter your name to log in : ";
    string Log_in;
    getline(cin,Log_in);

    cout<<" Enter your log in Password : ";
    string log_password;
    getline(cin,log_password);


    int correct=0;

    while(correct!=1){

        if(New_Name==Log_in && Password==log_password){

            correct=1;
        }else{

            cout<<" Your user name and password is incorrect !! "<<endl;
    cout<<" Enter your name to log in : ";
    getline(cin,Log_in);
    cout<<" Enter your log in Password : ";
    getline(cin,log_password);

    break;

        }
    }

   N_Name=New_Name;
}

void Book_Issue(string book[100],string type[100],string author[100],int count ,int cont,string N_Name,string Book_Store[100],int &x,string Isuue_Book){

  ofstream file2(Isuue_Book);

    int m=0;
    int L=0;
    L=cont+count;
    int chk=0;
    string nme;

    cout<<" To confirm User Please Enter your Name : ";
    cin>>nme;

    cout<<" Following are the books we have : ";

    for(int i=0,j=0,k=0;i<L;i++,j++,k++){
            cout<<endl;
        cout<<"Book"<<i+1<<endl;
        cout<<"    Name : "<<book[i]<<endl;
        cout<<"    Type : "<<type[j]<<endl;
        cout<<"    Author : "<<author[k]<<endl;
           cout<<endl;
    }

     cout<<" Enter the number of book you want to take (eg 1,2,3,.. etc) : ";
    int Book_No;
    cin>>Book_No;
    int num=0;
    num=Book_No-1;

    for(int i=0;i<L;i++){

        if(book[i]==book[num]){

            chk++;
        }
    }

    if(chk>0){

        Book_Store[x]=book[num];
        cout<<"The Book '"<<Book_Store[num]<<"' has been issued to "<<nme<<endl;

         book[num]="ISSUED";
         type[num]="ISSUED";
         author[num]="ISSUED";


        x++;

    }else{

    cout<<" Book is not avaliable !!"<<endl;

    }

    for(int i=0;i<x;i++){

        file2<<Book_Store[i]<<"  "<<nme<<endl;
    }



}

void Return(string Book_Store[100],int x,int i,string Book[100],string File_Name, string Isuue_File,int cont,int count,string type[100],string author[100]){

ofstream file2(Isuue_File);

int L=0;
L=cont+count;

  cout<<" Following are the books we have : ";
for(int j=0;j<x;j++){

        cout<<endl;
        cout<<"Book"<<j+1<<endl;
        cout<<"    Name : "<<Book_Store[j]<<endl;

}

 cout<<" Enter the number of book you want to Return (eg 1,2,3,.. etc) : ";
    int Book_No;
    cin>>Book_No;
    int num=0;
    num=Book_No-1;

    Book[i]=Book_Store[num];
    Book_Store[num]="Returned";

    for(int i=0;i<x;i++){

    file2<<Book_Store[i]<<endl;

    }


}

int main( ){


    string book[100];
    string type[100];
    string author[100];
    string Book_Store[100];
    string Book_Type[100];
    string Book_Author[100];
    string N_Name;
    string File_Name;
    string Isuue_File="Issued.txt";
    int check=0;
    int i=0,j=0,k=0,x=0,y=0,z=0;
    int count=0,cont=0;
    int L=0;

    cout<<"||**************************************************||ASSLAM-U-ALIKUM||***************************************||"<<endl<<endl;
    cout<<" To Start a Program First we have to enter a data !!"<<endl<<endl;
    cout<<" Enter the name of file where you want to store Data : ";
    cin>>File_Name;

    Collecting_Data(book,type,author,i,j,k,cont,File_Name);

   cout<<endl<<endl<<endl;

   int number=0;
    Menue1( );
   cout<<" Enter your option : ";
   cin>>number;

   while(number!=3){

    if(number==1){

        int option=0;
        cout<<endl;
        Liabrary_Menue( );
        cout<<" Enter your option : ";
        cin>>option;
        while(option!=4){

           if(option==1){
            ADD(book,type,author,i,j,k,count,File_Name);
           }
           if(option==2){

            Remove_Book(book,type,author,count ,cont,File_Name,L);
           }
            if(option==3){

            Edit_Book(book,type,author,count ,cont,File_Name);
           }
        cout<<endl;
        Liabrary_Menue( );
        cout<<" Enter your option : ";
        cin>>option;
        }

    }
    if(number==2){


             cout<<endl;
            Sign_Up(N_Name);
             cout<<endl;

            int Option=0;
            Menue2( );
            cout<<" Enter your Option : ";
            cin>>Option;
              while(Option!=3){
            if(Option==1){

       Book_Issue(book,type,author,count ,cont,N_Name,Book_Store,x,Isuue_File);

            }
            if(Option==2){

          Return(Book_Store,x,i,book,File_Name,Isuue_File,cont,count,type,author);
            }
        cout<<endl;
        Menue2( );
        cout<<endl;
            cout<<" Enter your Option : ";
            cin>>Option;
            }
    }
    cout<<endl;
    Menue1( );
    cout<<endl;
    cout<<" Enter your option : ";
    cin>>number;
   }



}
