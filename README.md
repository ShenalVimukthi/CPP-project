# CPP-project
This is my first project that I have done in my first year I used c++ programming language for it and it runs in terminal/shell


#include <iostream>
#include <vector>
#include <fstream>
#include <iomanip>
#include <conio.h>
#include <string>
#include <sstream>

using namespace std;

//main functions
void admin_2();//ok
void waiter_2();//ok
void customer_2();//ok
void greet();//ongoing
void Route();//ongoing


//public functions for all
void data_print(string,string);//ok
void WriteToFiles(string,string &,int &);//ok
void validate(string &,string);//ok
int * SpecCheck(string,string);//ok
void IntValidate(int&);//ok
void File_reset(string);//ok
void IndexRangeValidate(string,int &);//ok
bool isNum(string &);//ok
bool isStr(string &);//ok
void CinClear();//ok


//sub functions of admin function
void data_write(string,string,string,string,string,string);//ok
void fileEdit(string,string,string,string,string,string);//ok
void AddNew(string,string,string);//ok

//sub functions of waiter function
void WaiterValidate(string &,string);//ok
void get_data(string,int,string,string,string);//ok
void order(string,string,string,string,int,int &);//ok
void total_write(string,int &);//ok

//sub functions of customer function
void order_print(string,string);//ok
void Customer_Order_Add(string);//ok
void Cust_OrderFileWrite(string,string);//ok
void customer_order(string,int &);//ok






int main()
{
    //admin_2();//run ok
    //waiter_2();//run ok
    //customer_2();//run ok
    //greet();
    Route();
    return 0;
}

//greeting function top most function
void greet(){

   cout<<endl<<endl<<endl;
   cout<<R"(

                                                                          ##      ## ######## ##        ######   #######  ##     ## ########
                                                                          ##  ##  ## ##       ##       ##    ## ##     ## ###   ### ##
                                                                          ##  ##  ## ##       ##       ##       ##     ## #### #### ##
                                                                          ##  ##  ## ######   ##       ##       ##     ## ## ### ## ######
                                                                          ##  ##  ## ##       ##       ##       ##     ## ##     ## ##
                                                                          ##  ##  ## ##       ##       ##    ## ##     ## ##     ## ##
                                                                           ###  ###  ######## ########  ######   #######  ##     ## ########

            )"<<endl;
    cout<<endl<<endl<<endl;
    cout<<R"(

                                                                                         ######  ##     ## ##     ##  ######
                                                                                        ##    ## ##     ## ###   ### ##    ##
                                                                                        ##       ##     ## #### #### ##
                                                                                         ######  ##     ## ## ### ## ##   ####
                                                                                              ##  ##   ##  ##     ## ##    ##
                                                                                        ##    ##   ## ##   ##     ## ##    ##
                                                                                         ######     ###    ##     ##  ######

             )"<<endl;
     cout<<endl<<endl<<endl;
     cout<<R"(

                                                                  ######   #######  ######## ######## ##      ##    ###    ########  ########  ######
                                                                 ##    ## ##     ## ##          ##    ##  ##  ##   ## ##   ##     ## ##       ##    ##
                                                                 ##       ##     ## ##          ##    ##  ##  ##  ##   ##  ##     ## ##       ##
                                                                  ######  ##     ## ######      ##    ##  ##  ## ##     ## ########  ######    ######
                                                                       ## ##     ## ##          ##    ##  ##  ## ######### ##   ##   ##             ##
                                                                 ##    ## ##     ## ##          ##    ##  ##  ## ##     ## ##    ##  ##       ##    ##
                                                                  ######   #######  ##          ##     ###  ###  ##     ## ##     ## ########  ######










              )"<<endl;
      cout<<endl<<endl;
      cout<<"                                                                                Booting the system up PRESS ANY KEY TO CONTINUE...";
      getch();
      system("cls");

}
void Route(){
    //option selection variable
    int option;
    cout<<"                                                                                  SVMG Restaurant management system Route portal"<<endl;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl;
    cout<<"                                                                                               Good Day to you!"<<endl;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl;
    cout<<endl<<endl;
    cout<<"                                                                                           Please select the portal to run "<<endl;
    cout<<"                                                                                           --------------------------------"<<endl;
    cout<<"                                                                                                [1] Admin portal "<<endl;
    cout<<"                                                                                                [2] Waiter portal"<<endl;
    cout<<"                                                                                                [3] Customer portal"<<endl;
    cout<<"                                                                                           --------------------------------"<<endl;
    cout<<"                                                                                                Enter your selection:";
    IntValidate(option);
    CinClear();
    while(option>3||option<=0){
        cout<<"Enter a valid selection only 3 selections available : ";
        IntValidate(option);
        }




}

//full functions
void admin_2(){
    //admin_2 variables
    string cho="yes";
    string opt;

    cout<<"                                                                                  SVMG Restaurant management system Admin portal"<<endl;

    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl;

    cout<<"                                                                                          Food and beverage item details"<<endl;
    cout<<"                                                                                 -------------------------------------------------"<<endl;

    cout<<"        Enter the food items to console "<<endl;
    cout<<"After entering all items enter * mark to the console"<<endl;
    cout<<"===================================================="<<endl;

    //using a data_write function to minimize the code repetitions

    data_write("Enter the name of item ","Enter price for ","Rs.","Food_data.txt","Food_calc.txt","Food_calc_name.txt");

    system("cls");



    cout<<"        Enter the beverage items to console "<<endl;
    cout<<"After entering all items enter * mark to the console"<<endl;
    cout<<"===================================================="<<endl;


    data_write("Enter the name of item ","Enter price for ","Rs.","Beverage_data.txt","Beverage_calc.txt","Beverage_calc_name.txt");

    system("cls");



    cout<<"                                                                                                    Waiter details"<<endl;
    cout<<"                                                                                 -------------------------------------------------"<<endl;
    cout<<"                                                                                             Enter waiters to the list"<<endl<<endl;
    cout<<"After Entering all the waiters enter * mark to the console"<<endl;
    cout<<"=========================================================="<<endl;

    data_write("Enter the name of waiter ","Enter  index  of  ","ID.","Waiter_data.txt","waiter_backup.txt","Waiter_backup_name.txt");

    //End of data writing

    system("cls");


    //main do-while loop that keep admin controls running

    do{
        //start data priting

        //printing food data
        //using data_print function
        data_print("Food_data.txt","Food item menu");

        //print beverage data
        data_print("Beverage_data.txt","Beverage item menu");

        //print waiter data
        data_print("Waiter_data.txt","Waiter details");

        // data printing end



        cout<<endl<<endl;

        cout<<"                                                                                             -----------------------------"<<endl;

        //admin options
        //admin variables
        string select;
        int set=0;


        cout<<"                                                                                                   Advance options"<<endl;
        cout<<"                                                                                             -----------------------------"<<endl;

        cout<<"                                                                                                    Options    "<<endl<<endl;

        cout<<"                                                                                             [1] Update food menu       "<<endl;
        cout<<"                                                                                             [2] Update beverage menu   "<<endl;
        cout<<"                                                                                             [3] Add new food items     "<<endl;
        cout<<"                                                                                             [4] Add new beverage items "<<endl;
        cout<<"                                                                                             [5] Exit Admin portal      "<<endl<<endl;

        cout<<"                                                                                             ------------------------------"<<endl;

        cout<<"                                                                                                Enter prefered option :";
        //cin>>select;
        getline(cin,select);
        validate(select,"int");
        CinClear();
        cout<<"                                                                                             ------------------------------"<<endl;


        if(select=="1"){
            fileEdit("Food_data.txt","Rs.","food"," price","Food_calc_name.txt","Food_calc.txt");
            system("cls");
        }else if(select=="2"){
            fileEdit("Beverage_data.txt","Rs.","Beverage"," price","Beverage_calc_name.txt","Beverage_calc.txt");
            system("cls");
        }else if(select=="3"){
            AddNew("Food_data.txt","Rs.","food");
            system("cls");
        }else if(select=="4"){
            AddNew("Beverage_data.txt","Rs.","Beverage");
            system("cls");
        }else if(select=="5"){
            cout<<"Are you sure to exit from admin portal : ";
            string answer;
            cin>>answer;
            CinClear();
            validate(answer,"str");
            if(answer=="no"||answer=="NO"){
                system("cls");
                continue;
            }else if(answer=="yes"||answer=="YES"){
                system("cls");
                cout<<"Exiting from the admin portal..."<<endl;
                cout<<"    Have a good day..."<<endl;
                set=1;
                break;
            }
        }
        if(set!=1){
            cout<<"Do you need to keep the admin portal running (yes/no) : ";
            //cin>>cho;
            getline(cin,cho);
            validate(cho,"str");
            CinClear();
            system("cls");
        }


    }while(cho=="yes"||cho=="YES");

}
void waiter_2(){
    //fstream variable to handle files
    fstream File;
    //file data push variable
    string SendOut;

    cout<<"                                                                                  DVMG Restaurant management system Waiter portal"<<endl;


    //displaying the waiter details in the file

    data_print("Waiter_data.txt","Waiter details");

    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl;

    //looping variables
    string run="yes";
    string select;

    //integer convert variables
    int WaNo;
    cout<<"Please enter your waiter number in the que : ";
    string WaiterID;
    cin>>WaiterID;
    CinClear();
    //validate(WaiterID,"int");
    WaiterValidate(WaiterID,"int");
    CinClear();
    //converting the string variable to int after input validation
    WaNo=stoi(WaiterID);
    //validating the range of the Waiter index
    IndexRangeValidate("Waiter_data.txt",WaNo);

    system("cls");
    //looping starts

        while(run=="yes"||run=="YES"){
            cout<<"Please enter the table number that you are serving : ";
            string Tableno;
            cin>>Tableno;
            //validate(Tableno,"int");
            CinClear();
            WaiterValidate(Tableno,"int");
            CinClear();
            cout<<"Please enter the customer name                     : ";
            string custName;
            cin>>custName;
            getline(cin,custName);
            //validate(custName,"str");
            cout<<"Please enter customer contact number               : ";
            string contNo;
            cin>>contNo;
            //validate(contNo,"int");
            CinClear();
            WaiterValidate(contNo,"int");
            CinClear();
            system("cls");

            //writing the data into the Waiter_duty_record file
            get_data("Waiter_data.txt",WaNo,Tableno,custName,contNo);

            //waiter portal oreder section

            //order section
            //total calculating variable
            int total=0;

            //food ordering function

            //food item menu
            data_print("Food_data.txt","Food item menu");
            CinClear();

            order("food","Food_calc.txt","Food_calc_name.txt","Bill_data.txt",1,total);
            cout<<endl<<endl;
            system("cls");



            //beverage ordering function

             //beverage item menu
            data_print("Beverage_data.txt","Beverage item menu");

            order("beverage","Beverage_calc.txt","Beverage_calc_name.txt","Bill_data.txt",2,total);
            cout<<endl<<endl;
            system("cls");


            //finalizing the total and print it to the bill
            total_write("Bill_data.txt",total);
            //printing the finalize total to cache file
            total_write("Bill_data_cache.txt",total);

            //setting the display view
            cout<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl<<endl;

            //displaying the bill to the waiter
            File.open("Bill_data_cache.txt",ios::in);
            if(File.is_open()){
                while(getline(File,SendOut)){
                    cout<<"\t\t\t\t\t\t\t\t\t\t"<<SendOut<<endl;
                }
            }else{
                cout<<"Error !! The file did not opened correctly "<<endl;
            }
            File.close();

            //clearing the file
            File.open("Bill_data_cache.txt",ios::out);
            if(File.is_open()){
                File<<"             "<<endl;
            }else{
                cout<<"Error !! The file did not opened as expected"<<endl;
            }
            File.close();


            //looping question
            cout<<"\t\t\t\t\t\t\t\t\t\t"<<"Do you need to serve another table (yes/no):";
            cin>>run;
            //validate(run,"str");
            WaiterValidate(run,"str");
            CinClear();
            system("cls");


            if(run=="no"||run=="NO"){
                cout<<"\t\t\t\t\t\t\t\t\t\t"<<"       Exited from the waiter portal "<<endl;
                cout<<"\t\t\t\t\t\t\t\t\t\t"<<"            Have a good day !"<<endl;
                cout<<"\t\t\t\t\t\t\t\t\t\t"<<"     DVMG Restaurant management system"<<endl;
            }

        }





}
void customer_2(){

     //looping question variable
    string loop;
do{

    //string to int convert holder
    //int ConvInt;
    //rating variables
    int rate;

    //customer function variables
    string CustName,CustTel;

    //fstream variables
    fstream File;

    //string push out variables
    string SendOut;


    cout<<"                                                                                      DVMG Restaurant management system Customer portal"<<endl;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl<<endl;

    cout<<"                                                                                                 Welcome DVMG Restaurant "<<endl;
    cout<<"                                                                                                    Good Day to you !    "<<endl;

    //getting customer information
    cout<<"Please enter your name      : ";
    cin>>CustName;
    system("cls");
    cout<<endl<<endl<<endl<<endl;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl<<endl;
    cout<<"\t\t\t\t\t\t\t\t\t\t              "<<" Hi "<<CustName<<endl;
    cout<<"\t\t\t\t\t\t\t\t\t\t           "<<"Enter your telephone number : ";
    cin>>CustTel;
    validate(CustTel,"int");
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl<<endl;

    system("cls");
    cout<<endl<<endl;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl<<endl;
    cout<<"Customer Name      :"<<CustName<<endl;
    cout<<"Customer Telephone :"<<CustTel<<endl;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl<<endl;

    cout<<"\t\t\t\t\t\t\t\t\t\t "<<"     Place your order by refering the menus"<<endl;
    cout<<"\t\t\t\t\t\t\t\t\t\t "<<"     --------------------------------------"<<endl<<endl;


    //placing the order

    //food item menu
    data_print("Food_data.txt","Food item menu");

    //beverage item menu
    data_print("Beverage_data.txt","Beverage item menu");

    cout<<endl<<endl;;
    cout<<"---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------"<<endl<<endl;

    cout<<"\t\t\t\t\t\t\t\t\t\t "<<"   Be patient your waiter will arrive here soon "<<endl;
    cout<<"\t\t\t\t\t\t\t\t\t\t "<<"After your order arrived press any key to continue..."<<endl;
    getch();
    //rating the experience of the hotel
    cout<<"Rate our service on a scale 1-10 :";
    if(!(cin>>rate)){
    while(!(cin>>rate)){
            cout<<"Please enter an integer value no floats and letters allowed :";
            cin.clear();
            cin.ignore(123,'\n');
     }
    }
    while(rate<=0||rate>10){
            cout<<"The rate range is 1-10 please enter rating value inside the range :";
            while(!(cin>>rate)){
                cout<<"Please enter an integer value :";
                cin.clear();
                cin.ignore(123,'\n');
            }

    }


    //writing the rating to file
    File.open("customer_rating.txt",ios::out);
    if(File.is_open()){
        File<<"Customer name     :"<<CustName<<endl;
        File<<"Customer Telephone:"<<CustTel<<endl;
        File<<"Customer rating   :"<<rate<<endl;

    }else{
        cout<<"Error occured while accessing the file "<<endl;
    }
    File.close();

    cout<<"Press any key to set system for next customer "<<endl;
    getch();

    cout<<"Do you need to keep the customer portal running (yes/no) : ";
    cin>>loop;
    system("cls");
    }while(loop=="yes"||loop=="YES");


    }

//functions that run all over the programme
void data_print(string OutFile,string type){
    //fstream variable to access files
    fstream file;

    //string push out variable
    string SendOut;

    cout<<"\t\t\t\t\t\t\t\t\t\t\  "<<"-------------------------------------------------"<<endl;
    cout<<"\t\t\t\t\t\t\t\t\t\t\  "<<"                 "<<type<<endl;
    cout<<"\t\t\t\t\t\t\t\t\t\t\  "<<"-------------------------------------------------"<<endl;

    //opening the file to be displayed

    file.open(OutFile,ios::in);
    if(file.is_open()){
        //inside while counter
        int count=1;
        while(getline(file,SendOut)){
            cout<<"\t\t\t\t\t\t\t\t\t\t\  "<<" No."<<count<<" "<<SendOut<<endl;

            //counter increment

            count+=1;
        }
    }else{
        cout<<"Error ! file not opened "<<endl;
    }
    file.close();

}
void WriteToFiles(string FileName,string & PriOrName,int & index){
    //vectors
    vector <string> dataFile;

    //fstream variables
    fstream File;

    //string push out variables
    string SendOut;

    //length keeping variables
    float len;

    //opening the main data file to extract data

    File.open(FileName,ios::in);
    if(File.is_open()){
        while(getline(File,SendOut)){
            dataFile.push_back(SendOut);
        }
    }else{
        cout<<"Error ! occured while accesing the file "<<endl;
    }
    File.close();

    //writing the edited data into the vector
    dataFile[index]=PriOrName;

    //getting the lenght of the vector
    len=dataFile.size();

    //writing data into the file
    File.open(FileName,ios::out);
    if(File.is_open()){

        for(int i=0; i<len; i++){
            File<<dataFile[i]<<endl;
        }

    }else{
        cout<<"Error ! occured  while opening the file "<<endl;
    }
    File.close();


}
void validate(string & inData,string select){
    if(select=="str"){
        if(!(isStr(inData))){
            while(!(isStr(inData))){
                cout<<"!! Error invalid syntax please enter only alphabetical letters no spaces allowed !! : ";
                getline(cin,inData);
                CinClear();
            }
        }

    }else if(select=="int"){
        if(!(isNum(inData))){
            while(!(isNum(inData))){
                cout<<"!! Error invalid syntax please enter only integer values no floats allowed !! : ";
                getline(cin,inData);
                CinClear();
            }
        }
    }
    }
int * SpecCheck(string info,string FileName){
    //inside pointer
    int * OutInfo;
    //inside integer
    int InNo;
    cout<<"Enter the "<<info<<" number to be edited : ";
    //cin>>InNo;
    //IndexRangeValidate(FileName,InNo);
    while(!(cin>>InNo)){
        cout<<"Please enter an integer value : ";
        cin.clear();
        cin.ignore(123,'\n');
    }
    IndexRangeValidate(FileName,InNo);
    //CinClear();
    //cin.ignore(123,'\n');
    //setting the actual value of the vector index
    InNo-=1;
    //assigning the value for pointer
    OutInfo=&InNo;
    //returning the value got after checking as a pointer
    return OutInfo;
}
void File_reset(string FileName){
    fstream File;
    File.open(FileName,ios::out);
    if(File.is_open()){
        File<<" "<<endl;
    }else{
        cout<<"Error ! occured while opening the file "<<endl;
    }
    File.close();
}
void IndexRangeValidate(string FileName,int & index){
    //fastream variables
    fstream File;
    //vector
    vector <string> fileData;
    //length variables
    float len;
    //string push out variables
    string SendOut;

    File.open(FileName,ios::in);

    if(File.is_open()){
        while(getline(File,SendOut)){
            fileData.push_back(SendOut);
        }

    }else{

        cout<<"Error !! occured while accessing the file"<<endl;
    }
    File.close();

    len=fileData.size();

    while(index>len||index<=0){
        cout<<" Error !! Index invalid please enter an index between 1-"<<len<<" : ";
        while(!(cin>>index)){
            cout<<"Pleasse enter an integer value between range 1-"<<len<<" : ";
            cin.clear();
            cin.ignore(123,'\n');
        }
    }
    CinClear();

}
bool isNum(string & in){
    for(int i=0; i<in.length(); i++){
        if(!(isdigit(in[i]))){
            return false;
        }
    }
    return true;
}
bool isStr(string & get){
    for(char in:get){
        if(isdigit(in)){
            return false;
        }
    }
    return true;
}
void CinClear(){

    cin.clear();
}
void IntValidate(int& Num){
    if(!(cin>>Num)){
        while(!(cin>>Num)){
            cout<<"Please enter an integer value : ";
            cin.clear();
            cin.ignore(123,'\n');
        }
    }
}

//sub functions of admin function
void data_write(string type,string info,string add,string WriteFtype,string CalFile,string Calc_name){

    string take,value;
    float len;
    int count=0;


    vector <string> names;
    vector <string> Price_OrNo;

    while(take!="*"){
        cout<<type<<count+1<<setw(15)<<right<<" : ";
        //cin>>take;
        getline(cin,take);
        if(take=="*"){
            continue;
        }else{
            //validating inside the else
            validate(take,"str");
            CinClear();
        cout<<info<<setw(20)<<left<<take<<" : ";
        //cin>>value;
        getline(cin,value);
            validate(value,"int");
            CinClear();
        }
        count+=1;
        names.push_back(take);
        Price_OrNo.push_back(value);

        len=names.size();

        fstream Myfile;
        //opening user display file
        Myfile.open(WriteFtype,ios::out);

        if(Myfile.is_open()){

            for(int i=0; i<len; i++){
                Myfile<<setw(20)<<left<<names[i]<<setw(16)<<right<<add<<Price_OrNo[i]<<endl;
            }
        }
        //closing user display file
        Myfile.close();

        //calculation file data insert

        //inserting data for price file
        Myfile.open(CalFile,ios::out);
        if(Myfile.is_open()){
            for(int i=0; i<len; i++){
                //Myfile<<setw(20)<<left<<Price_OrNo[i]<<setw(10)<<right<<add<<names[i]<<endl;
                Myfile<<Price_OrNo[i]<<endl;
            }
        }
        //closing price file
        Myfile.close();

        //inserting data for name file
        Myfile.open(Calc_name,ios::out);
        if(Myfile.is_open()){
            for(int i=0; i<len; i++){
                Myfile<<names[i]<<endl;
            }
        }
        //closing name file
        Myfile.close();

    }

}
void fileEdit(string FileName,string method,string object,string PriOrNo,string EditNameFile,string EditPriceFile){
    //vectors
    vector <string> fileData;

    //Push out string variables
    string sendOut;

    //fstream variables
    fstream File;

    File.open(FileName,ios::in);
    if(File.is_open()){
        while(getline(File,sendOut)){
            fileData.push_back(sendOut);
        }
    }else{
        cout<<"Error ! occured while reading the file"<<endl;
    }
    File.close();

    //reading the data to a vector from the name file

    //end of reading to the vector

    //start of editing the file
    string selection;
    int * PointerHold;
    //pointer dereferencing variable
    int index;
    do{
        PointerHold=SpecCheck(object,FileName);
        //dereferencing the pointer and storing the value in index variable
        index=(*PointerHold);
        //validating the index range
        //IndexRangeValidate(FileName,index);
        //end of pointer return function
        CinClear();
        cin.ignore(123,'\n');
        cout<<"Enter the edited "<<object<<" name  : ";
        string itemName;
        //cin>>itemName;
        getline(cin,itemName);
        validate(itemName,"str");
        CinClear();
        //writing the edited data to Namefile
        WriteToFiles(EditNameFile,itemName,index);

        cout<<"Enter the edited "<<object<<PriOrNo<<" : ";
        string itemPrice;
        //cin>>itemPrice;
        getline(cin,itemPrice);
        validate(itemPrice,"int");
        CinClear();
        //writing the edited data to pricefile
        WriteToFiles(EditPriceFile,itemPrice,index);


        //opening the edit file
        File.open("Edit_file.txt",ios::out);
        if(File.is_open()){
            File<<setw(20)<<left<<itemName<<setw(16)<<right<<method<<itemPrice<<endl;
            // Myfile<<setw(20)<<left<<names[i]<<setw(10)<<right<<add<<Price_OrNo[i]<<endl;
        }else{
            cout<<"error ! occured while accessing the file "<<endl;
        }
        File.close();

        //opening the edit file to write inside the vector
        File.open("Edit_file.txt",ios::in);
        if(File.is_open()){
            string readOut;
            while(getline(File,readOut)){
                fileData[index]=readOut;
            }
        }else{
            cout<<"error ! occured while accessing the file "<<endl;
        }
        File.close();

        //length variables
        float length;
        length=fileData.size();

        //opening the original file to be edited
        File.open(FileName,ios::out);
        if(File.is_open()){
            for(int i=0; i<length; i++){
                File<<fileData[i]<<endl;
            }
        }else{
            cout<<"error ! occured while accessing the file "<<endl;
        }
        File.close();
        cout<<"Do you need to edit another item (yes/no) : ";
        //cin>>selection;
        getline(cin,selection);
        validate(selection,"str");
        CinClear();



    }while(selection=="yes"|selection=="YES");
}
void AddNew(string filename,string mode,string data){
    CinClear();
    fstream File;
    vector <string> DataFile;
    string SendOut;

    //start to get data from file to the vector
    File.open(filename,ios::in);
    if(File.is_open()){
        while(getline(File,SendOut)){
            DataFile.push_back(SendOut);
        }
    }else{
        cout<<"error ! occured while writing to the file "<<endl;
    }
    File.close();
    //end of data writing to the vector

    //creating a file to keep newly added items temporalily
    //do-while loop variable
    string sel;

    do{
        File.open("Temp_Data.txt",ios::out);
        if(File.is_open()){
            cout<<"Enter the "<<data<<" item to add  : ";
            string item;
            //cin>>item;
            getline(cin,item);
            //validate string
            validate(item,"str");
            CinClear();
            cout<<"Enter the price of "<<data<<" item : ";
            string itemprice;
            //cin>>itemprice;
            getline(cin,itemprice);
            //validate int
            validate(itemprice,"int");
            CinClear();
            File<<setw(20)<<left<<item<<setw(16)<<right<<mode<<itemprice<<endl;
            //File<<setw(20)<<left<<itemName<<setw(10)<<right<<method<<itemPrice<<endl;
        }else{
            cout<<"error ! while accessing the file "<<endl;
        }
        File.close();

        //opening the temp file to get data in it to the vector
        File.open("Temp_Data.txt",ios::in);
        if(File.is_open()){
            while(getline(File,SendOut)){
                DataFile.push_back(SendOut);
            }
        }else{
            cout<<"error ! occured while accessing the file "<<endl;
        }
        File.close();

        //writing into the original file
        File.open(filename,ios::out);
        if(File.is_open()){
            //getting the length of the vector to write data
            float lenght=DataFile.size();
            for(int i=0; i<lenght; i++){
                File<<DataFile[i]<<endl;
            }
        }else{
            cout<<"error ! occured while accessing the file "<<endl;
        }
        File.close();
        cout<<"Do you need to add another item (yes/no) :";
        //cin>>sel;
        getline(cin,sel);
        validate(sel,"str");
        CinClear();



    }while(sel=="yes"|sel=="YES");
}


//sub functions of waiter function
void WaiterValidate(string & input,string select){
    if(select=="str"){
        if(!(isStr(input))){
        while(!(isStr(input))){
            cout<<"!! Error invalid syntax please enter only alphabetical letters no spaces allowed !! : ";
            cin>>input;
            CinClear();
            }
        }
    }else if(select=="int"){
        if(!(isNum(input))){
            while(!(isNum(input))){
                cout<<"!! Error invalid syntax please enter only integer values no floats allowed !! : ";
                cin>>input;
                CinClear();
    }
}
    }
}
void get_data(string Name_File,int index,string serve_info,string CustName,string CustTel){
    fstream File;
    //string to push file data out
    string SendOut;
    //vectro to hold file data
    vector <string> hold;
    File.open(Name_File,ios::in);
    if(File.is_open()){
        while(getline(File,SendOut)){
            hold.push_back(SendOut);
        }
    }else{
        cout<<"Error ! File was not opened correctly"<<endl;
    }
    //closing the file after getting data to the vector
    File.close();

    //converting the index to its accurate value to match the index in vector
    index-=1;

    //opening the waiter duty record file
    File.open("Waiter_duty_record.txt",ios::app);
    if(File.is_open()){
        //setting file appearence
        File<<"              Waiter details"<<endl;
        File<<"----------------------------------------------"<<endl;
        File<<hold[index]<<endl;
        File<<"----------------------------------------------"<<endl;

        File<<"             Customer details"<<endl;
        File<<"----------------------------------------------"<<endl;

    }
    //closing the file to append table data again to the file
    File.close();

    //opening the file to append the table data
    File.open("Waiter_duty_record.txt",ios::app);
    if(File.is_open()){
        File<<"Table Number     : "<<serve_info<<endl;
        File<<"Customer Name    : "<<CustName<<endl;
        File<<"Customer Contact : "<<CustTel<<endl;
        File<<"----------------------------------------------"<<endl;
    }else{
        cout<<"Error ! while opening the file "<<endl;
    }
    //closing the file after appending the data
    File.close();
}
void order(string type,string PriceFile,string NameFile,string CalculateMethod,int instant,int & tot){
    //index string th
    //inside loop break variable
    string in;
    //inside int conversion variable
    int holder,qtyHolder;
    //inside counter
    int cnt=1;
    //inside file accessing variable
    fstream File;
    fstream File2;
    //file data holder vectors
    vector <int> hold;
    vector <string> NameHold;
    //file data pushing string variable
    string OutDat;
    //total calculation variable pointer

    //opening the file to extract price data into the vector
    File.open(PriceFile,ios::in);
    if(File.is_open()){
        while(getline(File,OutDat)){
            hold.push_back(stoi(OutDat));
        }
    }
    //closing the file after extracting the price data
    File.close();

    //opening the file to extract name data into the vector
    File.open(NameFile,ios::in);
    if(File.is_open()){
        while(getline(File,OutDat)){
            NameHold.push_back(OutDat);
        }
    }
    File.close();

    cout<<"     Enter the customer ordered "<<type<<" items "<<endl;
    cout<<"+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++"<<endl<<endl;
    cout<<"  After entering all the items enter * mark to the console  "<<endl;
    cout<<"+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++"<<endl<<endl;

    while(in!="*"){
        cout<<"Enter the index number of ordered "<<type<<" item "<<cnt<<" : ";
        cin>>in;
        if(in=="*"){
            continue;
        }else{
            //validate the data type
            WaiterValidate(in,"int");

            //vector index counter
            holder=stoi(in);
            //index range validation
            IndexRangeValidate(NameFile,holder);
            //converting the index counter to the actual value
            holder-=1;

            cout<<"Enter the ordered "<<type<<" item quantity : ";
            string qty;
            cin>>qty;

            CinClear();
            //validate the data type
            WaiterValidate(qty,"int");
            //convert quantity to integer value
            qtyHolder=stoi(qty);
            //counter increment
            cnt+=1;

            //calculating the order total and subtotal

            //opening a file to keep the calculated data
            File.open(CalculateMethod,ios::app);
            //opening the bill cache file to display the bill
            File2.open("Bill_data_cache.txt",ios::app);
            if(File2.is_open()){
                if(File.is_open()){
                    if(instant==1){
                        //setting and printing the bill

                        File<<"                    Calculated bill  "<<endl;
                        File2<<"                   Calculated bill  "<<endl;


                        File<<"------------------------------------------------------"<<endl;
                        File2<<"------------------------------------------------------"<<endl;


                        File<<setw(20)<<left<<"Item"<<setw(10)<<right<<"Qty(no)"<<setw(12)<<right<<"Price(Rs)"<<setw(13)<<right<<"Total(Rs)\n";
                        File2<<setw(20)<<left<<"Item"<<setw(10)<<right<<"Qty(no)"<<setw(12)<<right<<"Price(Rs)"<<setw(13)<<right<<"Total(Rs)\n";

                        File<<"------------------------------------------------------"<<endl;
                        File2<<"------------------------------------------------------"<<endl;


                    }

                    File<<setw(20)<<left<<NameHold[holder]<<setw(10)<<right<<qtyHolder<<setw(12)<<right<<hold[holder]<<setw(12)<<right<<hold[holder]*qtyHolder<<endl;
                    File2<<setw(20)<<left<<NameHold[holder]<<setw(10)<<right<<qtyHolder<<setw(12)<<right<<hold[holder]<<setw(12)<<right<<hold[holder]*qtyHolder<<endl;

                    //getting total
                    tot=tot+(hold[holder]*qtyHolder);
                    //setting the instant to stop the repeatition
                    instant=2;


                }
                File.close();
            }
            File2.close();

        }

    }
    //end of while loop




}
void total_write(string FileName,int & Tot){
    fstream File;
    File.open(FileName,ios::app);
    if(File.is_open()){
        File<<"------------------------------------------------------"<<endl;
        File<<setw(20)<<left<<"Subtotal"<<setw(34)<<right<<Tot<<endl;
        File<<"------------------------------------------------------"<<endl;
    }
    File.close();

}


//sub functions of customer function
void order_print(string PreWrittenFileName,string type){
    //inside variables
    string ItemNo;
    string qty;

    //file handling varibles
    fstream File;

    //counter
    //int cnt=1;


    //vectores
    vector <string> DataFile;
    vector <string> Indexing;

    //push out string variables
    string SendOut;

    //converted int holder
    int index;

    //opening the file to get data
    File.open(PreWrittenFileName,ios::in);
    if(File.is_open()){
        while(getline(File,SendOut)){
            DataFile.push_back(SendOut);
        }
    }else{
        cout<<"Error ! occured while writing to the file "<<endl;
    }
    File.close();


    cout<<"Enter the "<<type<<" items to order "<<endl;
    cout<<"++++++++++++++++++++++++++++++++++++"<<endl;
    cout<<endl<<endl;
    cout<<"After entering all the "<<type<<" items enter * mark to the console "<<endl;
    cout<<"++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++"<<endl<<endl;
    while(ItemNo!="*"){
    cout<<"Enter "<<type<<" item "<<" index number : ";
    cin>>ItemNo;
        if(ItemNo=="*"){
            continue;
        }else{
            validate(ItemNo,"int");
            //converting string to int
            index=stoi(ItemNo);
            //validating the index range
            IndexRangeValidate(PreWrittenFileName,index);
            //setting the index to its actual value
            index-=1;
            cin.clear();

            cout<<"Enter "<<type<<" item quantity : ";
            cin>>qty;
            validate(qty,"int");

            //openning the customer_order file to add orders
            File.open("Customer_order_list.txt",ios::app);
            if(File.is_open()){

                File<<setw(20)<<left<<DataFile[index]<<setw(10)<<right<<qty<<endl;

            }else{
                cout<<"Error ! occured while opening the file"<<endl;
            }
            File.close();
        }
    }



}
void Customer_Order_Add(string FileName){

    //fstream variable
    fstream File;

    //vector
    vector <string> filedata;

    //string push out variable
    string SendOut;

    //option select variables
    string select;

    //int convertion hold variable


    //writing the customer ordered list to a vector

    File.open(FileName,ios::in);
    if(File.is_open()){
        while(getline(File,SendOut)){
            filedata.push_back(SendOut);
        }
    }else{
        cout<<"Error ! occured while opening the file "<<endl;
    }
    cout<<"                                                                                                Add your items please"<<endl;
    cout<<"                                                                                                   [1] Food item    "<<endl;
    cout<<"                                                                                                   [2] Beverage item"<<endl;
    cout<<"                                                                                                  Select what to add :";
    cin>>select;
    validate(select,"int");
    if(select=="1"){
        Cust_OrderFileWrite("Food_calc_name.txt","Food");


    }else if (select=="2"){
        Cust_OrderFileWrite("Beverage_calc_name.txt","Beverage");

    }


}
void Cust_OrderFileWrite(string FileName,string Type){
    //correction counter
    int cnt=0;
    //looping variables
    string choice;


    //length variables
    float len;

    //data push out variables
    string SendOut;

    //vectors
    vector <string> filedata;
    vector <string> OrderFile;

    //fstream variables
    fstream File;

    //item hold variables
    string index;
    string qty;

    //string to int convert holder
    int indexHold;

    do{

        cout<<"Enter "<<Type<<" item index to add : ";
        cin>>index;
        validate(index,"int");
        indexHold=stoi(index);

        cout<<"Enter "<<Type<<" Quantity to add   : ";
        cin>>qty;
        validate(qty,"int");

        //opening item file to get the data by using the index

        File.open(FileName,ios::in);
        if(File.is_open()){
            while(getline(File,SendOut)){
                filedata.push_back(SendOut);
            }
        }
        else{
            cout<<"Error ! occured while opening the file "<<endl;
        }
        File.close();

        //oppening the order file to add them to a vector

        File.open("Customer_order_list.txt",ios::in);
        if(File.is_open()){
            while(getline(File,SendOut)){
                OrderFile.push_back(SendOut);
            }
        }else{
            cout<<"Error ! occured while opening the file"<<endl;
        }
        File.close();

        //writing the added item to the vector
        OrderFile.push_back(filedata[indexHold]);

        //getting the length of the vector to run the writing
        len=OrderFile.size();

        //write the added items to the original file
        File.open(FileName,ios::out);
        if(File.is_open()){
            for(int i=0; i<len; i++){
                File<<OrderFile[i]<<endl;
            }
        }else{
            cout<<"Error ! occured while accessing the file "<<endl;
        }
        File.close();

        cout<<"Do you need to add another "<<Type<<" item (yes/no) :";
        cin>>choice;
        validate(choice,"str");

    }while(choice=="yes"||choice=="YES");


}
void customer_order(string FileName,int & cnt){

    //fstream variable
    fstream File;

    //string push out variable
    string SendOut;
    File.open(FileName,ios::in);
    if(File.is_open()){
        cout<<"\t\t\t\t\t\t\t\t\t\t\t"<<setw(21)<<left<<"Item"<<setw(16)<<right<<"Quantity"<<endl<<endl;
        while(getline(File,SendOut)){
            if(cnt==0){
                cnt++;
                continue;
            }else{
                cout<<"\t\t\t\t\t\t\t\t\t\t\t"<<" No."<<cnt<<" "<<SendOut<<endl;
                cnt++;
            }

        }
    }else{
        cout<<"Error ! occured while opening the file "<<endl;
    }


}




