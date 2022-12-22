# Online-Examination
import java.util.*;
class Online_Examination
{
    Scanner sc = new Scanner(System.in);

    HashMap<String,Integer> info = new HashMap<String,Integer>();
    public void login()
    {
        info.put("Shubhangi", 1234);
        info.put("Gauri",    6789);
        info.put("Chanchal",   1122);
        info.put("Poorva",     1112);
        info.put("Bhavana",   1111);
        String id;
        int pwd;

        System.out.println("Please Login !");
        System.out.println("Enter User Name:");

        id = sc.next();
        System.out.println("Enter Password:");

        pwd = sc.nextInt();
        if(info.containsKey(id) && info.get(id)==pwd)
        {
            System.out.println("\nYou have Successfully Logged in To The Exam!");
            menu();
        }
        else
        {
            System.out.println("\nIncorrect User Name/ID Or Password!\nEnter With Correct Credentials!\n");
            login();
        }
    }
    public void menu()
    {
        int ch;
        System.out.println("\nEnter Your Choice:");
        System.out.println("1.Update/Reset Profile \n2.Start Exam \n3.Logout");
        ch = sc.nextInt();
        switch(ch)
        {
            case 1:
                info = update();
                menu();
                break;
            case 2:
                startExam();
                menu();
                break;
            case 3:
                System.exit(0);
                break;
            default:
                System.out.println("Choose a valid operation!");
        }
    }
    public HashMap<String,Integer> update()
    {
        String update_id;
        int update_pwd;
        System.out.println("Enter username/ID:");
        update_id = sc.next();
        System.out.println("Enter old password:");
        update_pwd = sc.nextInt();
        if(info.containsKey(update_id) && info.get(update_id)==update_pwd)
        {
            System.out.println("Enter New password:");
            update_pwd = sc.nextInt();
            info.replace(update_id,update_pwd);
            System.out.println("Your Password Reset Successfully!");
        }
        else
        {
            System.out.println("User Data Not Found!\n");
        }
        return info;
    }
    public void startExam()
    {
        long startTime = System.currentTimeMillis();
        long endTime = startTime + 30;
        int score = 0,ans;

        System.out.println("Instructions:(Attention)");
        System.out.println("1. Carry all necessary material");
        System.out.println("2. Read the Question Paper carefully");
        System.out.println("3. All Questions Are Compulsory");
        System.out.println("4. Make Strategy for writing an answer");
        System.out.println("5. Manage your time");
        System.out.println("\n All The Best!\n");
        System.out.println("----Exam has started----");
        while(System.currentTimeMillis()<endTime)
        {
            System.out.println("*********************");
            System.out.println("Q1.What is the extension of Java code files");
            System.out.println("1. .js \t2. .java \t3. .class\t4. .txt");
            System.out.print("Answer:");
            ans = sc.nextInt();
            if(ans == 2)
                score+=5;
            else
                score--;

            System.out.println("********* NEXT QUESTION **********");
            System.out.println("Q2.Who is the father of Python?");
            System.out.println("1.James Goslin\t2.Guido van Rossum\t3.Dennis Ritchie\t4.Brendan Eich");
            System.out.print("Answer:");
            ans = sc.nextInt();
            if(ans == 2)
                score+=5;
            else
                score--;

            System.out.println("********* NEXT QUESTION **********");
            System.out.println("Q3.Which of the following is not a Java Feature?");
            System.out.println("1.Object-Oriented\t2.Use of Pointers\t3.Portable\t4.Dynamic and Extensible");
            System.out.print("Answer:");
            ans = sc.nextInt();
            if(ans == 2)
                score+=5;
            else
                score--;

            System.out.println("********* NEXT QUESTION **********");
            System.out.println("Q4.Which of the following is not a OOPs concept");
            System.out.println("1.Abstraction\t2.Encapsulation\t3.Polymorphism\t4.Compilation");
            System.out.print("Answer:");
            ans = sc.nextInt();
            if(ans == 4)
                score+=5;
            else
                score--;

            System.out.println("********* NEXT QUESTION **********");
            System.out.println("Q5.In JAVA, The Dynamic Array Are Known AS: ");
            System.out.println("1.Kubernates\t2.Remote\t3.Vectors\t4.Cycle");
            System.out.print("Answer:");
            ans = sc.nextInt();
            if(ans == 3)
                score+=5;
            else
                score--;
            System.out.println("*******************");
            break;
        }
        System.out.println("You have Submitted Answers");
        System.out.println();
        System.out.println("Your Score is "+score);
        if(score>10)
            System.out.println("Congratulations , You're passed!");
        else
            System.out.println("Better Luck, Try again!");
    }
    public static void main(String args[])
    {
        Online_Examination obj = new Online_Examination();
        obj.login();
    }
}
