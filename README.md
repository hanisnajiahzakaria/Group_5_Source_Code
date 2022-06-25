# Group_5_Source_Code

This is Group 5 Project repository :smile:

//documentation section
/*Group5_Project_SourceCode : Hanis Najiah Binti Zakaria(S21A0066)
                              Nur Asfariena Binti Rosaimy(S21A0043)
                              Siti Nur Kamariah Binti Ab Rasid(S21A0055)
                              Nur Athirah Binti Mohd Rosley(S21B0044)
                              Siti Zulaikha Binti Muhamat Joohari(S21B0081)*/

//pre-processor section
#include<stdio.h>
#include<string.h>
#include<conio.h>

//global variable section
int totalCost = 0;
int a[9];
int cost[] = {35, 50, 15, 55, 50, 28};
char items[6][100]={"SEROJA BLOUSE",
                        "MELUR BLOUSE",
                        "LILI BLOUSE",
                        "VOIR JEANS",
                        "ESSE ONE PANTS", "PRINCESS SKIRT"};

char mail[100];

void cart(char *str, int choice)
{
    printf("\t\t\t\t%s's cart\n\n",str);
    printf("Id\tItems\t\t\tQuantity\t\t\tCost\n");

    for(int i= 0; i<=6; i++)
    {
        if(a[i]!=0)
        {
            printf("%d\t%s\t\t\t%d\t\t\t%d\n",i,items[i],a[i],(cost[i]*a[i]));
        }
    }
}

void payment(char *str, int choice, int totalCost, char *mail)
{
    cart(str,choice);
    printf("\n\n\t\t\t\t\t\t\tAmount to be Paid: %d\n" , totalCost);
    printf("Please Enter an Email : ");
    scanf(" %s" ,&mail);

    printf("Thank You %s For Choosing Us. We Sent an E-mail to proceed the Payment." ,str);

}

void deleteItem(char *str, int choice)
{
    int id;
    cart(str,choice);

    printf("\nEnter id to delete item : ");
    scanf("%d",&id);

    if(id<=6 && id>=0)
    {
        totalCost=totalCost-(cost[id]*a[id]);
        a[id]=0;
    }
    else
    {
        printf("Enter Valid id\n");
    }
        printf("Revised Items \n");
        
}

void displayItem()
{
    printf("|---------------------------------------------------------------------------------|\n");
    printf("|\t      item\t\t\t|\t      Price\t\t\t  |\n");
    printf("|---------------------------------------------------------------------------------|\n");
    printf("| TOP :\t\t\t\t\t|\t\t\t\t\t  |\n|\t1. SEROJA BLOUSE\t\t|\t     RM 35.00\t\t\t  |\n");
    printf("|\t2. MELUR BLOUSE\t\t\t|\t     RM 50.00\t\t\t  |\n");
    printf("|\t3. LILI BLOUSE\t\t\t|\t     RM 25.00\t\t\t  |\n");
    printf("|---------------------------------------------------------------------------------|\n");
    printf("| BOTTOM :\t\t\t\t|\t\t\t\t\t  |\n|\t4. VOIR JEANS \t\t\t|\t     RM 55.00\t\t\t  |\n");
    printf("|\t5. ESSE ONE PANTS\t\t|\t     RM 50.00\t\t\t  |\n");
    printf("|\t6. PRINCESS SKIRT\t\t|\t     RM 28.00\t\t\t  |\n");
    printf("|---------------------------------------------------------------------------------|\n");
}

void purchase(char *str)
{
    int top, num, bottom;
    char answ;
    int choice;
    //int a[9];
    

    
        do
        {
            printf("\nEnter (1 - TOP / 2 - BOTTOM) : ");
            scanf("%d",&choice);

            if(choice ==1)
            {
                printf("Enter number : (1 - SEROJA BLOUSE - RM35 / 2 - MELUR BLOUSE- RM50 / 3 - LILI BLOUSE - RM25) :");
                scanf("%d", &top);

                if(top == 1)
                {
                    printf("\nYou chose SEROJA BLOUSE with RM35");
                    a[0]++;
                    totalCost+=35;
                }
                else if(top == 2)
                {
                    printf("\nYou chose MELUR with RM50");
                    a[1]++;
                    totalCost += 50; 
                    
                }
                else if(top == 3)
                {
                    printf("\nYou chose LILI BLOUSE with RM25");
                    a[2]++;
                    totalCost+=25;
                    
                }  
            }
            else if(choice == 2)
            {
                printf("Enter number : (4 - VOIR JEANS - RM55 / 5 - ESSE ONE PANTS - RM50 / 6 - PRINCESS SKIRT - RM28) :");
                scanf("%d", &bottom);

                if(bottom == 4)
                {
                    printf("\nYou chose VOIR JEANS for RM55");
                    a[3]++;
                    totalCost += 55;
                }
                else if(bottom == 5)
                {
                    printf("\nYou chose ESSE ONE PANTS for RM50");
                    a[4]++;
                    totalCost += 50;
                }
                else if(bottom == 6)
                {
                    printf("\nYou chose PRINCESS SKIRT for RM28");
                    a[5]++;
                    totalCost += 28;
                }
            }
            printf("\nAre sure To continue(Y/N)? : ");
            scanf(" %c", &answ);
        } while (answ =='Y');

        printf("\n\nThe Purchase has been add to cart,");
        printf("\nYour Cost in Cart should be RM %d \n\n",totalCost);

        getch();
        cart(str, choice);
        printf("\n\t\t\t\t\t\t\t Amouunt = RM %d \n\n",totalCost);

        printf("\nTo Edit the List in Cart item Choose Menu 2.");
        printf("\n\t\tOR\n");
        printf("To Continue Shopping Choose Menu 1.");
        printf("\n\t\tOR\n");
        printf("To proceed with Payment Choose Menu 3.");

}

//main function section
int main()
{

    //int totalCost;
    int bottom;
    int i,j,choice,c=1,a[9],cost[9];
    char mail[100];

    char str[100];
    char items[9][100]={"SEROJA BLOUSE",
                        "MELUR BLOUSE",
                        "LILI BLOUSE",
                        "VOIR JEANS",
                        "ESSE ONE PANTS",
                        "PRINCESS SKIRT",};

        printf("\nPlease Enter Your Name : ");
        gets(str);
        printf("\n\t\t\t\tHello %s, \n\t\t\tWELCOME TO SAYANG ONLINE BOUTIQUE.\n",str);

    do
    {
            getch();
            printf("\n\n1 - Purchasing Item\n2 - Edit Cart\n3 - To Proceed Payment\n4 - To Exit\n");
            printf("Enter choice : ");
            scanf("%d",&choice);
            printf("\n");
        

        switch(choice)
        {
            case 1:
            displayItem();
            purchase(str);
            break;

            case 2: 
            deleteItem(str,choice);
            printf("\n");
            cart(str,choice);
            printf("\nTo Continue Shopping Choose Menu 1.");
             printf("\nTo Proceed Payment Choose Menu 2.");
            break;

            case 3 :
            payment(str,choice,totalCost,mail);
            break;

            case 4:
            printf("\nExit The System");
        }
       

    } while (choice != 4);
    
    
}

//user-defined section
