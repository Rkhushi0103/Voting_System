# Voting_System
The Online Voting System is a simple Java-based application that allows users to conduct a voting process digitally. The system allows adding candidates, casting votes, counting votes, and displaying the winner. 

import java.util.*;
class Candidate {
 String name;
 int votes;
Candidate(String name) {
 this.name = name;
 this.votes = 0;
 } }
public class OnlineVotingSystem {
public static void main(String[] args) {
Scanner sc = new Scanner(System.in);
 ArrayList<Candidate> candidates = new ArrayList<>();
 while (true) {
 System.out.println("\n--- Online Voting System ---");
 System.out.println("1. Add Candidate");
 System.out.println("2. Vote for Candidate");
 System.out.println("3. Show Vote Count");
 System.out.println("4. Display Winner");
 System.out.println("5. Exit");
 System.out.print("Enter your choice: ");
 int choice = sc.nextInt();
 sc.nextLine();
 switch (choice) {
 case 1:
 System.out.print("Enter candidate name: ");
 String name = sc.nextLine();
 candidates.add(new Candidate(name));
 System.out.println("Candidate added successfully.");
 break;
 case 2:
 if (candidates.size() == 0) {
 System.out.println("No candidates available.");
 break; }
 System.out.println("Candidates List:");
 for (int i = 0; i < candidates.size(); i++) {
 System.out.println((i + 1) + ". " + candidates.get(i).name); }
 System.out.print("Enter candidate number to vote: ");
 int vote = sc.nextInt();
 if (vote > 0 && vote <= candidates.size()) {
 candidates.get(vote - 1).votes++;
 System.out.println("Vote recorded.");
 } else {
 System.out.println("Invalid candidate."); }
 break;
 case 3:
 System.out.println("\nVote Count:");
for (Candidate c : candidates) {
 System.out.println(c.name + " - " + c.votes + " votes"); }
 break;
 case 4:
 if (candidates.size() == 0) {
 System.out.println("No candidates available.");
 break; }
 Candidate winner = candidates.get(0);
 for (Candidate c : candidates) {
 if (c.votes > winner.votes) {
 winner = c; } }
 System.out.println("Winner is: " + winner.name + " with " + winner.votes + " votes.");
 break;
 case 5:
 System.out.println("Exiting...");
 System.exit(0);
 default:
 System.out.println("Invalid choice."); } } } }
