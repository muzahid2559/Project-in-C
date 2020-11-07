#include<stdio.h>
//#include<conio.h>
int list();
void deposit();
void withdraw();
void transfer();
void checkdetails();
void last();
int TotalAmount = 10000, TotalDeposit = 0, TotalWithdraw = 0, TotalTransfer = 0, Amount, WithdrawAmount,TransferAmount;
int AccountNumber;
char a[50];
void main(){
    //clrscr();
    printf("\nEnter your name: ");
    scanf("%s",a);
    printf("\nEnter your account namber: ");
    scanf("%d", &AccountNumber);
    while(1){
    //clrscr();
    switch(list()){
    case 1:
        deposit();
        TotalDeposit = TotalDeposit + Amount;
        break;
    case 2:
        withdraw();
        if(WithdrawAmount <= TotalAmount){
        TotalWithdraw = TotalWithdraw + WithdrawAmount;
        }
        break;
    case 3:
        transfer();
        if(TransferAmount <= TotalAmount){
        TotalTransfer = TotalTransfer + TransferAmount;
        }
        break;
    case 4:
        checkdetails();
        break;
    case 5:
        //clrscr();
        last();
        //getch();
        exit(0);
    default:
        printf("Wrong Choice\n");
        //getch();
    }
}
}
int list(){
    int ch;
    printf("1. Deposit Amount:\n");
    printf("2. Withdraw Amount:\n");
    printf("3. Transfer Amount:\n");
    printf("4. Check Details:\n");
    printf("5. exit:\n");
    printf("\nEnter Your choice: ");
    scanf("%d",&ch);
    return(ch);
}
void deposit(){
    printf("\nEnter the amount you want to deposit: ");
    scanf("%d",&Amount);
    TotalAmount = TotalAmount + Amount;
}
void withdraw(){
    printf("\nEnter the amount you want to withdraw: ");
    scanf("%d",&WithdrawAmount);
    if(WithdrawAmount <= TotalAmount){
    TotalAmount = TotalAmount - WithdrawAmount;
    }
    else{
    printf("Less amount,Withdraw is not possible!\n");
    }
}
void transfer(){
    printf("\nEnter the amount you want to transfer: ");
    scanf("%d",&TransferAmount);
    if(TransferAmount <= TotalAmount){
    TotalAmount = TotalAmount - TransferAmount;
    }
    else{
    printf("Less amount,transfer is not posible!\n");
    }
}
void checkdetails(){

    printf("\nTotal Amount:%d\n",TotalAmount);
    printf("Total Deposit:%d\n",TotalDeposit);
    printf("Total Withdraw:%d\n",TotalWithdraw);
    printf("Total Transfer:%d\n\n",TotalTransfer);
}
void last(){
    printf("\n***********************\n");
    printf("Your Name:%s\n",a);
    printf("Account Number:%d\n",AccountNumber);
    printf("Total Amount:%d\n",TotalAmount);
    printf("Total Deposit:%d\n",TotalDeposit);
    printf("Total Withdraw:%d\n",TotalWithdraw);
    printf("Total Transfer:%d\n",TotalTransfer);
    printf("\n\n******* Thanks ********\n");
}
