#include <stdio.h>
#include <stdlib.h>
#include <strings.h>
#include <windows.h>
#include <time.h>
//Structures below;
	struct bookdata {
		char book[30];
		int stock;
	};
	
	struct profile {
		char roll[15];
		char name[30];
	};
//Structures above;

int newbie;
//////////////////////////////////////////////////
void studentUI();
void login();
void registration();
void adminUI();
void adminpassword();
void program_control();
void pc_UI();
void staff_tracking();
void book_tracking();
void add_books(struct bookdata *d,int);
void remove_books(struct bookdata *d,int);
void student_tracking();
void student_profile();

////////////////////////////////////////////////
void studentUI() {
	//This is student UI
	 student_ui:
        printf("");
        int student_input;
        printf("\n\n\n\n\n");
        printf("\t -----------------------------------------------\n");
        printf("\t|\t~~~~~~~~~~Welcome Student~~~~~~~~~~\t|\n");
        printf("\t|\tPress 1 For login\t\t\t|\n");
        printf("\t|\tPress 2 for Registration\t\t|\n");
        printf("\t|\tPress 3 to go back\t\t\t|\n");
        printf("\t|\t\t\t\t\t\t|\n");
        printf("\t -----------------------------------------------\n");
        printf("\n\n\n\n\n\n\n");
        
        if (newbie == 1)
        	printf("\tSelect your purpose.....\n\n\n\n");
    
        printf("\tInput Section\n\t");
        student_input = getche(); system("cls");
		//condition of student's input
        switch(student_input) {
        	case '1':
        		system("cls");
        		login();		 //login section here
        		break;
        	case '2':
        		system("cls");
        		registration();  //registration section here
        		break;
        	case '3':
        		system("cls");
        		main();		 //goes back
        		break;
        	default:
        		system("cls");
        		goto student_ui; //default
		}
}
void login() {
	printf("\n\n\n\n\n");
        printf("\t -----------------------------------------------\n");
        printf("\t|\t~~~~~~~~~~Welcome Student~~~~~~~~~~\t|\n");
        printf("\t|\tEnter Your ULID:\t\t|\n");
        printf("\t|\tEnter Your TCIOE Roll Number:\t\t\t|\n");
        printf("\t|\t\t\t\t\t\t|\n");
        printf("\t -----------------------------------------------\n");
        //check the database for the information and see if it matches with the input data
        //system("cls");
}
void registration() {
	printf("\n\n\n\n\n");
        printf("\t -----------------------------------------------\n");
        printf("\t|\t~~~~~~~~~~Welcome Student~~~~~~~~~~\t|\n");
        printf("\t|\tEnter your Name:\t\t\t|\n");
        printf("\t|\tEnter Your TCIOE Roll Number:\t\t|\n");
        printf("\t|\tEnter Your Date of Birth:\t\t|\n");
        printf("\t|\t\t\t\t\t\t|\n");
        printf("\t -----------------------------------------------\n");
        //system("cls");
}


void adminUI() {
	 char admin_input;
	 
        admin_ui:
        
		if (newbie == 1)	
			printf("\t\t\t\t\t\t\t\t\t\t\t\t\t\tpassword");
		
        printf("\n\n\n\n\n");
        printf("\t -----------------------------------------------\n");
        printf("\t|\t~~~~~~~~~~Welcome Librarian~~~~~~~~~~\t|\n");
        printf("\t|\t\t\t\t\t\t|\n");
        printf("\t|\tPress 1 to Enter the Passcode:\t\t|");
        printf("\n\t|\t\t\t\t\t\t|\n");
        printf("\t|\tPress 2 to go back:\t\t\t|\n");
        printf("\t -----------------------------------------------\n");
        printf("\n\n\n\n\n\n\n");
        
        if (newbie == 1)
        	printf("\tGot the passcode? You are all set....\n\n\n\n");
        	
        printf("\tInput Section\n\t");
        admin_input = getche(); system("cls");
        //condition of admin's input
        switch(admin_input) {
    		case '1':
    			system("CLS");
    			adminpassword();//takes to admin password check
    			break;
    		case '2':
    			system("CLS");
    			main();		//goes back
    			break;
    		default:
    			system("CLS");
    			goto admin_ui;  //default
		}
}

void adminpassword() {
	fflush(stdin);
	char password[9];
	printf("Enter the PassWord (8 words) [Automatic Promt If Correct Code]: ");
	pass(password);	
	if ( strcmp(password,"password")== 0)
    {
    	system("CLS");
        program_control();
    }else{
        printf("\n\n\n\t\t\t\t\tWrong password!!\n\n");
        printf("\n\n\n\t\t\t\t\tPress any Key to Continue.....");
        getch();
        system("CLS");
        adminUI();
    }
}

void program_control() {
	system("CLS");
	pc_UI();
}

void pc_UI() {
	int input;
		control:
	
		printf("\n\n\n\n\n");
        printf("\t ---------------------------------------------------------------\n");
        printf("\t|\t~~~~~~~~~~~~~Welcome Librarian~~~~~~~~~~~~~\t\t|\n");
        printf("\t|\t\t\t\t\t\t\t\t|\n");
        printf("\t|\t\t     This Is Control Station.\t\t\t|\n");
        printf("\t|\t\t\t\t\t\t\t\t|\n");
        printf("\t|\t1. Staff tracking");
        printf("\t\t2. Book Tracking\t|\n");
        printf("\t|\t3. Student Tracking");
        printf("\t\t4. Check Reports\t|\n");
        printf("\t|\t\t\t      5. Exit\t\t\t\t|\n");
        printf("\t|\t\t\t\t\t\t\t\t|\n\t|\t\t\t\t\t\t\t\t|\n");
        printf("\t ---------------------------------------------------------------\n");
        printf("\n\n\n\n\n\n\n");
        printf("\tInput Section\n\t");
		input = getche(); system("cls");
		
		char choise;
	switch(input) {
		case '1':
			system("cls");
			staff_tracking();
			system("cls");
			goto control;
			break;
		case '2':
			system("cls");
			book_tracking();
			system("cls");
			goto control;
			break;
		case '3':
			system("cls");
			student_tracking();
			system("cls");
			goto control;
			break;
		case '4':
			system("cls");
			check_reports();
			system("cls");
			goto control;
			break;
		case '5':
			printf("\n\n\tAre you sure to quit?(Y/N): ");
			choise = getche();
			while (choise == 'y' || choise == 'Y') {
				exit(0);
			}
			system("cls");
			 goto control;
			break;
		default:
			system("cls");
			goto control;
			
	}
}
void staff_tracking() {
	printf("\n\n\n\n\n\n\n\t\tDue to technical and privacy concerns. Staff Tracking is no longer available...\n");
	printf("\t\t\tWe are sorry for your discomfort...  :( ");
	getch();
	program_control();
}

 void book_tracking() {
	printf("\n\n\t\t\tThis is Book Tracking Section:\n\n");
	printf("\n\nPress any Key to Continue....");
	getch();
	system("CLS");
	printf("\n\n");
	
	struct bookdata d[7];
	FILE *rbook;
	rbook = fopen("Data/bookdata.txt","r");
	if (rbook == NULL) {
		printf("\n\n\tThe registry not found. Contact the EMIS unit.(Well, if you know what to do JUST DO IT!)");
		delay(1);
		exit(0);
	}
		if(newbie == 1)
			printf("\n\n\tFirst column is for book code, second column for book name and the third for available stocks...\n\n\n");
	//////
	label:
	//////
		for (int i=0; i<6; i++) {
			fscanf(rbook,"%s",d[i].book);
			fscanf(rbook,"%d",&d[i].stock);
			printf("%d %s ",i+1,d[i].book);
			printf("%d\n",d[i].stock);
		}
	fclose(rbook);
	///////
	manual:
	////////
	printf("\n\n\n");
	printf("\t\t1.Manual Edit(add)");
	printf("\t\t2. Manual Edit(remove)");
	printf("\t\t3. Go Back\n");
	int input = getche();

	int sc,factor;
	switch(input) {
		case '1':
			fflush(stdin);
			sc=0;
			printf("Enter subject code(1-6): ");
			scanf("%d",&sc);
			switch(sc) {
				case 1:
					add_books(&d,sc);
					break;
				case 2:
					add_books(&d,sc);
					break;
				case 3:
					add_books(&d,sc);
					break;
				case 4:
					add_books(&d,sc);
					break;
				case 5:
					add_books(&d,sc);
					break;
				case 6:
					add_books(&d,sc);
					break;
				default:
					system("cls");
					goto manual;
			}
			//
			getch();
			system("cls");
			goto label;
			break;
		case '2':
			fflush(stdin);
			sc=0;
			printf("\nEnter subject code(1-6): \ns");
			scanf("%d",&sc);
			switch(sc) {
				case 1:
					remove_books(&d,sc);
					break;
				case 2:
					remove_books(&d,sc);
					break;
				case 3:
					remove_books(&d,sc);
					break;
				case 4:
					remove_books(&d,sc);
					break;
				case 5:
					remove_books(&d,sc);
					break;
				case 6:
					remove_books(&d,sc);
					break;
				default:
					system("cls");
					goto manual;
			}
			//
			getch();
			system("cls");
			goto label;
			break;
		case '3':
			system("cls");
			program_control();
			break;
		default:
			system("cls");
			//
			goto label;		
	}
}

void add_books(struct bookdata *d ,int sc){
		FILE *wbook;
		wbook = fopen("Data/bookdata.txt","w+");
		
		int i,factor;
		i = sc-1;
		printf("The number of books added is: ");
		scanf("%d",&factor);
		d[i].stock += factor;
			for (int j=0; j<6; j++) {
				if (j == i){
					fprintf(wbook,"%s\t",d[i].book);
					fprintf(wbook,"%d\n",d[i].stock);
				}else{
					fprintf(wbook,"%s\t",d[j].book);
					fprintf(wbook,"%d\n",d[j].stock);
				}
			}
		printf("The book of %s has available %d number.",d[i].book,d[i].stock);	
		fclose(wbook);		
}	

void remove_books(struct bookdata *d ,int sc){
		FILE *wbook;
		wbook = fopen("Data/bookdata.txt","w+");
		int i,factor;
		i = sc-1;
		printf("The number of books borrowed is: ");
		scanf("%d",&factor);
		d[i].stock -= factor;
			for (int j=0; j<6; j++) {
				if (j == i){
					fprintf(wbook,"%s\t",d[i].book);
					fprintf(wbook,"%d\n",d[i].stock);
				}else{
					fprintf(wbook,"%s\t",d[j].book);
					fprintf(wbook,"%d\n",d[j].stock);
				}
			}
		printf("The book of %s has available %d number.",d[i].book,d[i].stock);	
		fclose(wbook);		
}	
void student_tracking() {
	student_profile();
}

void student_profile(){
	system("cls");
	struct profile {
		char roll[15];
		char name[30];
	};
	typedef struct profile profile;
	profile d[48];
	FILE *read9;
	read9 = fopen("Data/students.txt","r");
	if (read9 == NULL) {
		printf("The registry not found. Contact the EMIS unit.(Well, if you know what to do JUST DO IT!)");
		exit(0);
	}
	
		for (int i=0; i<=48; i++) {
			fscanf(read9,"%s",d[i].roll);
			fscanf(read9,"%[^\n]s",d[i].name);
			printf("%s",d[i].roll);
			printf("%s\n",d[i].name);
		}
	manual:
		
	printf("\n\n\n");
	printf("\t\t1.Manual Search");
	printf("\t\t2. Go Back\n");
	int input = getch();
	
	char roll[15];	
	switch(input) {
		case '1':
			printf("\nEnter the student's roll number: ");
			scanf("%s",&roll);
				for(int j=0; j <= 48-1; j++) {
					if (strcmp(roll, d[j].roll) == 0 ){	
					printf("The entry of student %s is found.",d[j].name);
					}
				}                                                                   
			getch();
			goto manual;
			break;
		case '2':
			program_control();
			break;
		default:
			student_profile();
	}
}


void check_reports() {
	
	printf("\n\n\t\t\tThis is Report & Review Section:\n\n");
	printf("\n\nPress any Key to Continue....");
	getch();
	system("CLS");
	printf("\n\n");
	int input;
	
	///////
	report:
	///////
	printf("\n\n\n");
	printf("\t\t1.Issue Regarding Books");
	printf("\t\t2.Issue Regarding Entry");
	printf("\t\t3.Issue Regarding Program\n");
	printf("\t\t4.Report an error ");
	printf("\t\t5.Go Back \n");
	
	input = getche(); system("cls");
	///////////////////////////////
	void book_error();
	void human_error();
	void program_error();
	void report_error();
	///////////////////////////////
	switch(input) {
		case '1':
			system("cls");
			book_error();
			getch();
			system("cls");
			goto report;
			break;
		case '2':
			system("cls");
			human_error();
			getch();
			system("cls");
			goto report;
			break;
		case '3':
			system("cls");
			program_error();
			getch();
			system("cls");
			goto report;
			break;
		case '4':
			system("cls");
			report_error();
			getch();
			system("cls");
			goto report;
			break;
		case '5':
			system("cls");
			program_control();
			break;
		default:
			goto report;
	}
}

void book_error() {
	char c;
	printf("\n\nPress any Key to continue....");
	system("cls");
	printf("\n\n");
	FILE *read0;
	read0 = fopen("Data/Report/book_error.txt","r");
		if (read0 == NULL) {
			printf("The registry not found. Contact the EMIS unit.(Well, if you know what to do JUST DO IT!)");
			exit(0);
		}
		while ( (c = fgetc(read0)) != EOF)
			printf("%c",c);	
	fclose(read0);
}

void human_error() {
	char c;
	printf("\n\nPress any Key to continue....");
	system("cls");
	printf("\n\n");
	FILE *read8;
	read8 = fopen("Data/Report/human_error.txt","r");
		if (read8 == NULL) {
			printf("The registry not found. Contact the EMIS unit.(Well, if you know what to do JUST DO IT!)");
			exit(0);
		}
		while ( (c=fgetc(read8)) != EOF)
			printf("%c",c);	
	fclose(read8);
}

void program_error() {
	char c;
	printf("\n\nPress any Key to continue....");
	system("cls");
	printf("\n\n");
	FILE *read7;
	read7 = fopen("Data/Report/human_error.txt","r");
		if (read7 == NULL) {
			printf("The registry not found. Contact the EMIS unit.(Well, if you know what to do JUST DO IT!)");
			exit(0);
		}
		while ( (c=fgetc(read7)) != EOF)
			printf("%c",c);	
	fclose(read7);
}

void report_error() {
	time_t  t;
	time(&t);
	char error[200];
	printf("\n\nPress any Key to continue....");
	system("cls");
	printf("\n\n");
	FILE *write0;
	write0 = fopen("Data/Report/report_error.txt","a");
	printf("\nWe are extremely sorry for the existence of error.\n\n");
	printf("Please mention your error here: \a\n");
	scanf("%[^\n]s",&error);
	getch();
	printf("\nThank You for Your Review. Have a Good Day!");
	fprintf(write0,"\n\n");
	fprintf(write0,"%s",ctime(&t));
	fprintf(write0,"\n\t%s\n",error);
	fclose(write0);
}
void main() {
	SetColor(2); //color changer 1=dark blue,2=green,3=blue,4=red,5=purple,6=yellow,7=while,8=grey,9=bright blue
    //This is the main (first) User Interface
    
    //newbiee(); //Interface for first time user
    system("cls");
    int input;
    main_label:
    do
    {
        printf("\n\n\n\n\n");
        printf("\t -----------------------------------------------\n");
        printf("\t|\t~~~~~~~~~~~~~Welcome~~~~~~~~~~~~~\t|\n");
        printf("\t|\t\t\t\t\t\t|\n");
        printf("\t|\tThis Is Thapathali College Library.\t|\n");
        printf("\t|\tSelect your Account Type\t\t|");
        printf("\n\t|\t\t\t\t\t\t|\n");
        printf("\t|\t1. Student");
        printf("\t\t2. Librarian\t|\n");
        printf("\t|\t3. Exit\t\t\t\t\t|\n");
        printf("\t|\t\t\t\t\t\t|\n\t|\t\t\t\t\t\t|\n");
        printf("\t -----------------------------------------------\n");
        printf("\n\n\n\n\n\n\n");
        
        if (newbie == 1)
        	printf("\tAs stated, choose the account type....\n\n\n\n");
        
		printf("\tInput Section\n\t");
        input = getche();system("cls");
        if (input == '1' || input == '2'|| input == '3')
            break;
    }
    while (input);
	
	int choice;
    switch(input) {
    	case '1':
    		system("CLS");
    		studentUI();   //takes to student UI
    		break;
    	case '2':
    		system("CLS");
    		adminUI();		//takes to admin UI
    		break;
    	case '3':
 			printf("\n\n\tAre you sure to quit?(Y/N): ");
			choice = getch();
			while (choice == 'y' || choice == 'Y') {
				exit(0);
			}
			main();
    	default:
    		system("CLS");
    		goto main_label;
	}
}
/*
void newbiee() {
    FILE *r, *w;
    r= fopen("Data/newbie.txt","r");
    fscanf(r,"%d",&newbie);
    fclose(r);
    
    if (newbie == 1) {
    w=fopen("Data/newbie.txt","w");
    fprintf(w,"%d",newbie+1);
    fclose(w);
    }
        if (newbie == 1) {
        printf("Welcome to Thapathali College Virtual Library System.\n\n");
        printf("Our system detected that this is your first time in this virtual environment.\n\n");
        printf("\t\tLet's give you a quick tour.\n\n");
        printf("After this window you will be prompted to the major interface, where it becomes necessary to choose account type.\n");
        printf("Students require their ULID which is their library identity(also their IOE roll no.) \n");
        printf("\tWhile librarian has his password which lets him access to a lot of student-library information.");
        printf("\n\n\t\t See you a while later!!");
    }
    printf("\n\n\n\nPress any Key to Continue.........");
    getch();
}
*/
void pass(char password[]) {
	char ch;
	for (int i=0; i<8;i++) {
		ch = getch();
		password[i]=ch;
		ch='*';
		printf("%c",ch);
	}
}
//text color function
void SetColor(int ForgC)
 {
 WORD wColor;

  HANDLE hStdOut = GetStdHandle(STD_OUTPUT_HANDLE);
  CONSOLE_SCREEN_BUFFER_INFO csbi;

                       //We use csbi for the wAttributes word.
 if(GetConsoleScreenBufferInfo(hStdOut, &csbi))
 {
                 //Mask out all but the background attribute, and add in the forgournd color
      wColor = (csbi.wAttributes & 0xF0) + (ForgC & 0x0F);
      SetConsoleTextAttribute(hStdOut, wColor);
 }
 }
// end of text color function
 
 
/////////////////////////////////////////////////////////////////statement delaying function,just use delay(time) 
void delay(int number_of_seconds)						/////////							 time= no of seconds
{														/////////
    // Converting time into milli_seconds				/////////
    int milli_seconds = 1000 * number_of_seconds;		/////////
  														/////////
    // Storing start time								/////////
    clock_t start_time = clock();						/////////
  														/////////
    // looping till required time is not achieved		/////////
    while (clock() < start_time + milli_seconds)		/////////
        ;												/////////
}														/////////
/////////////////////////////////////////////////////////////////
