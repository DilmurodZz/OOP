#ifndef ACCOUNT_H
#define ACCOUNT_H


#include <iostream>
#include <string>
using namespace std;


class Account {
protected:
   string ownerName;
   double balance;


public:
   Account(string name = "", double bal = 0.0) : ownerName(name), balance(bal) {}


   double getBalance() const {
       return balance;
   }


   virtual void display() const {
       cout << "Owner: " << ownerName << endl;
       cout << "Balance: " << balance << endl;
   }


   virtual ~Account() {
       cout << "Account closed for " << ownerName << endl;
   }


   Account operator+(const Account& other) const {
       Account temp;
       temp.ownerName = this->ownerName;
       temp.balance = this->balance + other.balance;
       return temp;
   }


   Account operator-(const Account& other) const {
       Account temp;
       temp.ownerName = this->ownerName;
       temp.balance = this->balance - other.balance;
       return temp;
   }


   bool operator==(const Account& other) const {
       return this->balance == other.balance;
   }


   friend ostream& operator<<(ostream& out, const Account& acc) {
       out << "Owner: " << acc.ownerName << endl;
       out << "Balance: " << acc.balance << endl;
       return out;
   }


   friend istream& operator>>(istream& in, Account& acc) {
       in >> acc.ownerName >> acc.balance;
       return in;
   }
};


class SavingsAccount : public Account {
private:
   double interestRate;


public:
   SavingsAccount(string name = "", double bal = 0.0, double rate = 0.0)
       : Account(name, bal), interestRate(rate) {}


   void display() const override {
       cout << "Owner: " << ownerName << endl;
       cout << "Balance: " << balance << endl;
       cout << "Interest Rate: " << interestRate << "%" << endl;
   }
};


class CheckingAccount : public Account {
private:
   double transactionFee;


public:
   CheckingAccount(string name = "", double bal = 0.0, double fee = 0.0)
       : Account(name, bal), transactionFee(fee) {}


   void display() const override {
       cout << "Owner: " << ownerName << endl;
       cout << "Balance: " << balance << endl;
       cout << "Transaction Fee: " << transactionFee << endl;
   }
};


#endif



