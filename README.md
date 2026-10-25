include<iostream>
using namespace std;

int main(){
    int rows = 6; 
    
    
    for (int i =1; i<= rows; i++){
    
    for (int j=1; j<= i; j++){
        cout<<" * ";
             }
             cout<< endl;
    }
    return 0;
    }









    
    
    
    
#include<iostream>
using namespace std;

int main(){
    int rows = 6;
    
    for(int i=1; i<= rows; i++){
         
         for(int s =1; s<=rows -i; s++){
             cout<<"  ";
         }
         for(int j =1; j<= i; j++){
             cout<<" * ";
         }
         cout<<endl;
    }
         return 0;
    }










    const int LED_COUNT =3;
const int ledPins[LED_COUNT]={13,12,11}; //Array of pin numbers 
int current =0;// which LED is lit now 

void allOff(){
  for(int i = 0; i< LED_COUNT; i++){
    digitalWrite(ledPins[i], LOW);
  }
}

void lightOne(int index, int ms){ 
  allOff();
  digitalWrite(ledPins[index], HIGH);
  delay(ms); 
}

int nextIndex(int index){
  return (index + 1)% LED_COUNT;
}

void setup(){
  for (int i =0; i<LED_COUNT; i++){
    pinMode(ledPins[i],OUTPUT);
}
Serial.begin(9600);
}

void loop(){
  lightOne(current,300);
  Serial.print("Lit LED on pin");
  Serial.println(ledPins[current]);
  current = nextIndex(current);
  
}
