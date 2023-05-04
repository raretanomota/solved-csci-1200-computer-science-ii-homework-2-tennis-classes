Download Link: https://assignmentchef.com/product/solved-csci-1200-computer-science-ii-homework-2-tennis-classes
<br>
In this assignment you will parse and compute statistics from the results of recent <em>Grand Slam </em>tennis championships (the Australian Open, the French Open, Wimbledon, and the U.S. Open). Scoring and determining the winner of a tennis match is quite complex, but we have summarized everything you need to know to complete this assignment. Please read the entire handout before starting to code the assignment.

<h1>Tennis Scores</h1>

Here’s a crash course in tennis scoring: A <em>match </em>between two players consists of a number of <em>sets</em>. For men’s Grand Slam events, the first player to win three sets is the winner of the match (a.k.a., the best of five). Each set in the match consists of a number of <em>games</em>. The first player to win six games is the winner of the set, but the player must win by two games. If the set score gets to 6-5 (or 5-6), the players play a twelfth game. If the set score is 7-5 (or 5-7), the set is over. If the players are tied at 6-6 they play a special game called a <em>tiebreak </em>and the winner of the tiebreak wins the set, 7-6 (or 6-7). At the Australian Open, there is a special exception and in the fifth set they do not play a tiebreak. They just keep playing regular games until one player is ahead by two games (resulting in some fantastic 5 hour matches!) More details on the tennis scoring system are available here: http://en.wikipedia.org/wiki/Tennis_score. As an example of the input you will be parsing, here is the result of the recent men’s final at the 2006 Australian Open:

Roger Federer d. Marcos Baghdatis 5-7 7-5 6-0 6-2

In this match, player <em>Roger Federer </em>defeated player <em>Marcos Baghdatis </em>in a four set match. Baghdatis won the first set (it was close). Federer won the second set (it was also close). In the third set Baghdatis didn’t win any games and in the last set he only won two games.

<h1>File I/O and Command Line Arguments</h1>

Your program will run with two command-line arguments, one being the input file containing the match information and the other being the output file where you will write the computed statistics. Example input and output files are posted on the course website. For example, here is a valid command line to your program: tennis_statistics.exe sample_scores.txt sample_scores_out.txt

We have provided you with a few tennis score datasets. The original data was taken from an online resource: http://stevegtennis.com/. The format has been modified slightly to ease parsing. Each match is listed on a separate line. The winner is always listed first. Each player has a first name and a last name (two strings). The special string “d.” is placed between the two names. Each set is a string concatenating the number of games the first player won with the number of games the second player won, with the character “-” between.

<h1>Statistics Collected and Output</h1>

The output will be in <em>three parts</em>. First is a table with the players ordered by the <strong>percentage of matches </strong>they won. Each row of the table should include the player, the number of matches won, the number of matches lost and the percentage of matches won. You should do a little bit of nice formatting to this output (see the example code from lecture). For example, given an input file with these matches:

Marcos Baghdatis d. Radek Stepanek 6-4 6-3 3-6 0-6 7-5

David Nalbandian d. Danai Udomchoke 6-2 6-2 1-6 6-7 6-1

Marcos Baghdatis d. Ivan Ljubicic 6-4 6-2 4-6 3-6 6-3 Marcos Baghdatis d. David Nalbandian 3-6 5-7 6-3 6-4 6-4

Your program will produce a table similar to this:

<table width="245">

 <tbody>

  <tr>

   <td width="126">MATCH STATISTICS</td>

   <td width="31"> </td>

   <td width="25"> </td>

   <td width="63"> </td>

  </tr>

  <tr>

   <td width="126">Player</td>

   <td width="31">W</td>

   <td width="25">L</td>

   <td width="63">percentage</td>

  </tr>

  <tr>

   <td width="126">Marcos Baghdatis</td>

   <td width="31">3</td>

   <td width="25">0</td>

   <td width="63">1.000</td>

  </tr>

  <tr>

   <td width="126">David Nalbandian</td>

   <td width="31">1</td>

   <td width="25">1</td>

   <td width="63">0.500</td>

  </tr>

  <tr>

   <td width="126">Danai Udomchoke</td>

   <td width="31">0</td>

   <td width="25">1</td>

   <td width="63">0.000</td>

  </tr>

  <tr>

   <td width="126">Radek Stepanek</td>

   <td width="31">0</td>

   <td width="25">1</td>

   <td width="63">0.000</td>

  </tr>

  <tr>

   <td width="126">Ivan Ljubicic</td>

   <td width="31">0</td>

   <td width="25">1</td>

   <td width="63">0.000</td>

  </tr>

 </tbody>

</table>

The formatting shown above is an example, your output may be formatted differently, as long as it satisfies the description above. The second part of the output is a table with the players ordered by the <strong>percentage of games </strong>they won. As in the first part, each row lists the player, the number of games won, the number of games lost and the percentage of games won. Here’s the output for the data above:

<table width="245">

 <tbody>

  <tr>

   <td width="119">GAME STATISTICS</td>

   <td width="31"> </td>

   <td width="31"> </td>

   <td width="63"> </td>

  </tr>

  <tr>

   <td width="119">Player</td>

   <td width="31">W</td>

   <td width="31">L</td>

   <td width="63">percentage</td>

  </tr>

  <tr>

   <td width="119">David Nalbandian</td>

   <td width="31">49</td>

   <td width="31">44</td>

   <td width="63">0.527</td>

  </tr>

  <tr>

   <td width="119">Radek Stepanek</td>

   <td width="31">24</td>

   <td width="31">22</td>

   <td width="63">0.522</td>

  </tr>

  <tr>

   <td width="119">Marcos Baghdatis</td>

   <td width="31">73</td>

   <td width="31">69</td>

   <td width="63">0.514</td>

  </tr>

  <tr>

   <td width="119">Ivan Ljubicic</td>

   <td width="31">21</td>

   <td width="31">25</td>

   <td width="63">0.457</td>

  </tr>

  <tr>

   <td width="119">Danai Udomchoke</td>

   <td width="31">18</td>

   <td width="31">25</td>

   <td width="63">0.419</td>

  </tr>

 </tbody>

</table>

The third and final part of the output is a chance for you to be creative. You will collect and output some other statistic from the matches. A simple example would be to output the players ordered by the percentage of sets won. A more complex example would be to find all the matches where the ultimate winner lost the first set and output the players who most often “come from behind to win”.

Extra credit will be awarded to particularly interesting statistics that require clever programming. The most important task for the this part of the assignment is to write a concise description (<em>&lt; </em>100 words) of your new statistic. Put this description in your <em>plaintext </em>file named README.txt along with any other notes for the grader. Be sure to tell the grader which dataset best demonstrates your new statistic. Feel free to create your own dataset and include it with your submission.

<h1>Useful Code</h1>

To control the formatting of your tables, you’ll want to read up on the various iomanipulators: std::setw(int), std::setprecision(int), and std::fixed. And don’t forget about the sort function that can be used to order the contents of a vector. To help you parse a string from the input file that represents a set, we provide the following code to get you started:

// Parses a string that represents a set (i.e., “6-3”) by breaking the

// string into two substrings and converting those strings to // integers, which are returned via call-by-reference parameters void parse_set(std::string &amp;set, int &amp;games_won, int &amp;games_lost) {

int i = set.find(’-’); games_won = atoi(set.substr(0,i).c_str()); games_lost = atoi(set.substr(i+1,set.size()-i-1).c_str());

}

You do not need to fully understand the details of this function in order to use it as a <em>black box</em>. With the code above and the &lt;&lt; stream function for strings used in lecture you can implement all of the parsing necessary for this assignment. <em>Hint: </em>By looking at the results of the first 3 sets, you can determine whether a 4th set was played and you should read in another set <em>or </em>whether the match was over after 3 sets and next string contained in the file is part of the next match. In fact, your code will not care about newlines in the input file.

<h1>Program Requirements &amp; Submission Details</h1>

Your program should involve the definition of <em>at least one class </em>that has its own .h and .cpp files, named appropriately. Initially you should focus on the dataset of matches that required 5 sets. Once that is working you can extend your solution to handle all matches.

Do all of your work in a folder named hw2 inside of your CSII homeworks directory. Use good coding style when you design and implement your program. Be sure to make up new test cases and don’t forget to comment your code! Please use the provided template README.txt file for any notes you want the grader to read. <strong>You must do this assignment on your own, as described in the “Academic Integrity for Homework” handout. If you did discuss the problem or error messages, etc. with anyone, please list their names in your </strong>README.txt <strong>file. </strong>When you’ve finished writing, testing, debugging, and commenting your code, prepare and submit your assignment as instructed on the course webpage. Please ask a TA if you need help preparing your assignment for submission or if you have difficulty writing portable code.

2