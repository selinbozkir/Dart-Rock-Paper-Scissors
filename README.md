# DartProjects
import 'dart:math';
import 'dart:io'; 

enum choice {Rock, Scissors, Paper} 

void main() {
 int playerScore = 0; 
 int cScore = 0; 
 var round = 3; 

  stdout.write("Welcome to Rock-Paper-Scissors game. Please choose: r-s-p "); 
  stdout.write("If you want to exit the game, press e. \n"); 
  
while(true){

  final input = stdin.readLineSync(); 

  var playerChoice; 
  if(input=='r'){
    playerChoice = choice.Rock; 
  }
  else if(input=='p'){
    playerChoice = choice.Paper;
  }
  else if(input=='s'){
    playerChoice = choice.Scissors;
  }
  else if(input=='e'){
    break; 
  }
  else {
   print("Invalid input");
   break;
  }

  round--; 

  final rndNumber = Random().nextInt(3); 
  final cMove = choice.values[rndNumber]; 

  print("Your choice: $playerChoice"); 
  print("Computer: $cMove ");  
  print("Remaining round: $round");

  if(playerChoice == choice.Rock && cMove == choice.Scissors || 
    playerChoice == choice.Paper && cMove == choice.Rock || 
    playerChoice == choice.Scissors && cMove == choice.Paper ){
    playerScore++;
  }
  else if(playerChoice == cMove){
    print('Draw'); 
  }
  else {
     cScore++;
  }
  print("Your score - Computer socre $playerScore - $cScore");
  
  if(round==0){
  if(playerScore>cScore){
    print("Congrats, you win!"); 
  }
  else if(playerScore==cScore){
    print("Draw!");
  }
  else {
    print("You lost...");
  }
  if(round==0){
    break; 
  }
  }


}




  
}