# OASIS-TASK-4
import java.util.*;

public class OnlineExam {
    


Scanner sc = new Scanner(System.in);
HashMap<String,Integer> data = new HashMap<String,Integer>();

	public void login() {
		data.put("Jayesh",2343);
		data.put("PatilJayesh",2000);
		System.out.println("\n\n******WELCOME TO ONLINE EXAMINATION SYSTEM******");
		String UserId;
		int password;
		System.out.println("PLEASE CONTINUE TO LOGIN TO YOUR ACCOUNT");
		System.out.print("Enter UserName : ");
		UserId = sc.next();
		System.out.print("Enter password : ");
		password = sc.nextInt();
		if(data.containsKey(UserId) && data.get(UserId)==password) {
			System.out.println("\nLOGIN  SUCCESSFULL ");
				option_menu();
		}
		else {
			System.out.println("Oops! Something Went Wrong");
			System.out.println("Please Try Again");
				login();
		}
	}
	public void option_menu() {
		int select;
		System.out.println("\nEnter your choice");
		System.out.println("1.Update Profile and Password");
		System.out.println("2.Start Exam");
		System.out.println("3.Logout");
		select = sc.nextInt();
		switch(select) {
		case 1:
			data=update();
			option_menu();
			break;
		case 2:
			exam_que();
			option_menu();
			break;
		case 3:
			System.exit(0);
			break;
		default:
			System.out.println("Wrong Entry...Try Again");
		}
	}
	public HashMap<String,Integer> update(){
		String uUser;
		int upassword;
		System.out.println("Welcome to Update Profile");
		System.out.println("Enter Username");
		uUser = sc.next();
		if(data.containsKey(uUser)) {
		System.out.println("Enter new Password you to want to Update to your Profile");
		upassword = sc.nextInt();
		data.replace(uUser, upassword);
		}
		else {
			System.out.println("User with your Entered Credentials Doesn't Exist");
		}
		return data;
	}
public void exam_que() {
	long examtime=System.currentTimeMillis();
	long endtime=examtime+30;
	int ans_count=0;
	int ans,score;
	System.out.println("Start Your Exam");

	
//Question starts
	while(System.currentTimeMillis()<endtime) {
		System.out.println("You have 30 seconds to answer 5 questions");
		System.out.println("Each Question carries 10 marks"+" "+"-5 for wrong answer");
		System.out.println("Let's start your Attempt");
		System.out.println("Wish You A Good Luck!");
		System.out.println("\n\nQ.1) Who invented Java Programming?");
		System.out.println("\n(1) Guido van Rossum"+"\t"+"(2) James Gosling"+"\t"+"(3) Dennis Ritchie"+"\t"+"(4) None of these");
		System.out.println("Enter Correct Option");
		ans=sc.nextInt();
		System.out.println("Your Answer Was Saved");
		if(ans==2) {
			ans_count++;
		}
		System.out.println("\n\nQ.2)Which component is used to compile, debug and execute the java programs?");
		System.out.println("(1)JRE"+"\t"+"(2)JIT"+"\t"+"(3) JDK"+"\t"+"(4) JVM");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Your Answer Was Saved");
		if(ans==3) {
			ans_count++;
		}
		System.out.println("\n\nQ.3)Which of these cannot be used for a variable name in Java?");
		System.out.println("1) Identifier & keyword"+"\t"+"(2) Identifier"+"\t"+"(3)Keyword"+"\t"+"(4)None of the mentioned");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Your Answer Was Saved");
		if(ans==3) {
			ans_count++;
		}
		System.out.println("\n\nQ.4)What is the extension of java code files?");
		System.out.println("(1) .js"+"\t"+"(2) .txt"+"\t"+"(3) .class"+"\t"+"(4).java");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Your Answer Was Saved");
		if(ans==4) {
			ans_count++;
		}
		System.out.println("\n\nQ.5)Which exception is thrown when java is out of memory?");
		System.out.println("1)  MemoryError"+"\t"+"2) OutOfMemoryError"+"\t"+"3) MemoryOutOfBoundsException"+"\t"+"4) None of the above");
		System.out.println("Enter correct option");
		ans=sc.nextInt();
		System.out.println("Your Answer Was Saved");
		if(ans==2) {
			ans_count++;
		}
		break;
	}
	System.out.println("Well Tried!");
	System.out.println("You have done with your exam");
	score=ans_count*10-((5-ans_count)*5); 
	System.out.println("Your score is..."+" "+score+"/50");	
}
public static void main(String[] args) {
        OnlineExam log =new OnlineExam();
		log.login(); 
        
    }
    
}
