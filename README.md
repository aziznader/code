code
====
public class Game {


   public static void main(String[] args) {
   
  
   
   private static int play() {
   
      Deck deck = new Deck();  // Get a new deck of cards
      
      Card Current;  // The current card

      Card NxtCard;   // The next card in the deck.  
                      

      int Cguess ;  // The number of correct predictions 

      char Guess;   // The user's guess.  
      
      deck.shuffle();  // Shuffle the deck into a random order before
                      

      Cguess = 0;
      Current = deck.dealCard();
      TextIO.putln("The first card is the " + Current);
      
      while (true) {  // Loop ends when user's prediction is wrong.
         
         /* Get the user's prediction, 'H' or 'L' (or 'h' or 'l'). */
         
         TextIO.put("Will the next card be higher (H) or lower (L)?  ");
         do {
             Guess = TextIO.getlnChar();
             Guess = Character.toUpperCase(guess);


             if (Guess != 'H' && Guess != 'L') 


                TextIO.put("Please respond with H or L:  ");
         } while (Guess != 'H' && Guess != 'L');


         
         /* Get the next card  */
         
         NxtCard = deck.dealCard();
         TextIO.putln("The next card is " + NxtCard);


         
         /* Check user's answers. */
         
         if (NxtCard.getValue() == Current.getValue()) {
            TextIO.putln("The value is the same as the previous card.");
            TextIO.putln("You lost.  Sorry!");
            break;  
         }
         else if (NxtCard.getValue() > Current.getValue()) {


            if (Guess == 'H') {
                TextIO.putln("Answer is correct.");


                Cguess++;
            }
            else {
                TextIO.putln("Answer is wrong.");
                break;  // End the game.
            }
         }
         else {  
            if (guess == 'L') {
                TextIO.putln("Answer is correct.");
                Cguess++;
            }
            else {
                TextIO.putln("Answer is wrong.");
                break;  // End the game.
            }
         }
         
         /* Set up for the next iteration of the loop
            
         
         Current = NxtCard;
         TextIO.putln();
         TextIO.putln("The card is " + Current);
         
      } // end of while loop
      
      TextIO.putln();
      TextIO.putln("The game is over.");
      TextIO.putln("You made " + Cguess 
                                           + " correct predictions.");
      TextIO.putln();
      
      return Cguess;
      
   }  
   

} 
