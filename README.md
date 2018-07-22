# JDBC
# Database Management System

```
Bachelor of Engineering (2016-2020)
```
```
VRISHANK GUPTA (2016UCO1677)
```
```
COE 3
```
## DIVISION OF COMPUTER SCIENCE ENGINEERING

## NETAJI SUBHAS INSTITUTE OF TECHNOLOGY,

## DWARKA


## AIM & DESCRIPTION OF ENTITIES:

In this project of Cricket Database, the main aim was to get experience

of how we can relate Database Entities with Real Life Entities. Here in

our Project we have ICC Entity which control all Entities and acts as

Controlling Unit of the Cricket Database.

# ICC entity has Teams under it which has attributes like Team_id,

Captain, Rank, Country.

# Team consists of other major entities like Players, Managers, Coaches,

etc.

# Manager has attributes like Manager_id, teams, and Manager Name and

Coach Entity has attributes like Name, Join date, Coach_id, and country.

# Team also consists of another important entity, Players with attributes

like Name, Fitness Index, Age etc.

# Players are further divided into Batsman and Bowler with respective

descriptive attributes like no of runs scored, centuries etc for Batsman

and economy, no of wickets taken for Bowler.

# ICC hosts many Series which has Matches which decide the Rank of a

team in World.


**Relational Model(Normalisation Included)**

**Player:-**

In the above table “PLAYER” we see there are high
possibilities of data being redundant. So, we break the
“player” table into two smaller tables i.e. “Batsman” and
“Bowler”:-

###### Player

**Batsman Bowler**

The resultant “Player” table has following structure:-

The batsman and bowler table contains the following
attributes:-


**Bowler:-**

And has following Structure:-

**Batsman:-**

And has Following Structure:—


**Team:-**

The table “Teams” has following Initial structure where
information about each player has been stored in team’s
list:-

As we see that for each Player in the same team the
information would be repeated every time, so we decomposed
them into two separate tables where team id is taken as
foreign key in “player” table:-

##### Team

##### Player Team

So, the resulting “Team” table has following structure:-


And the resulting table “Players” has the already mentioned
structure which is follows:-

##### Coach:-

The table “Coach” has following Structure:-

Here attribute “team” is a foreign key which references
“Teams” table on TEAM_ID. Coach_id is taken as primary key
here.


##### Manager:-

The table “Manager” has following structure :-

Here attribute “team” is a foreign key which references
“Teams” table on TEAM_ID. Manager_id is taken as primary key
here.


##### Matches:-

The table matches has Following structure:-

Here, Match_ID is the primary key.

TEAM_1,TEAM_2 references the table “TEAMS”,

SERIES_ID references the table “Series”,

MAN_OF_THE_SERIES references the table “Player”.


##### Series:-

The table Series has following structure:-

Here attribute “WINNING_TEAM” is a foreign key which
references “Teams” table on TEAM_ID. Series_id is taken as
primary key here.


#### Conclusion:-

The final structure of complete database is as follows :-

### SOME SAMPLE QUERIES AND THEIR O/P:-


1.
Searching for a player in database:-

2.

Searching for a coach in database mapping with Team country:-


3.

INSERT INTO `BOWLER` (`ID`, `RANK`, `WICKETS`,
`NO_OF_MATCHES`, `5_WICKETS`, `ECONOMY`)
VALUES
(1,99,4,8,0,4),
(2,87,67,34,2,8),
(3,12,331,564,88,7),
(4,122,1,2,0,6),
(5,13,132,67,5,3),
(6,1,10,1,2,2),
(7,133,0,0,0,0),
(8,133,0,0,0,0),
(9,65,4,1,0,7),
(10,33,64,34,3,2),
(11,133,0,0,0,0),
(12,86,67,34,2,2),
(13,22,23,34,1,7),
(14,133,0,0,0,0),
(15,130,4,1,0,2),
(16,54,32,6,3,4),
(17,34,765,123,3,4);


4.

INSERT INTO `BATSMAN` (`ID`, `HUNDREDS`, `FIFTIES`, `RUNS`,
`NO_OF_MATCHES`, `RANK`)
VALUES
(1,12,65,4565,345,32),
(2,0,6,455,335,34),
(3,10,54,4425,344,35),
(4,78,633,4152,811,36),
(5,60,89,3214,465,39),
(6,3,54,5157,666,36),
(7,0,0,76,6,98),
(8,0,66,5422,189,38),
(9,33,654,6546,3444,22),
(10,21,13,890,67,5),
(11,33,87,565,454,55),
(12,0,0,0,0,89),
(13,0,0,23,11,90),
(14,327,984,85749,1000,1),
(15,1,2,422,5,80),
(16,0,0,76,43,101),
(17,0,5,877,9,99),
(18,40,12,543,33,3),
(19,33,22,23,23,2);


5.
INSERT INTO `PLAYER` (`PLAYER_ID`, `NAME`, `FITNESS`, `AGE`,
`DEBUT`, `TEAM`)
VALUES
(1,'DHONI',89,31,'2007-11-12',1),
(2,'kohli',87,22,'2010-01-23',1),
(3,'rohit',78,32,'2001-08-30',1),
(4,'TENDULKAR',99,14,'1999-12-01',1),
(5,'RAHUL',78,30,'2002-09-05',1),
(6,'VIRAT',97,28,'2012-02-02',1),
(7,'dhawan',100,29,'2015-12-01',1),
(8,'ashwin',98,27,'2008-04-26',1),
(9,'bumrah',89,21,'2007-11-19',1),
(10,'ganguly',69,22,'2013-10-18',1),
(11,'GEETU',1,19,'2017-11-11',1),
(12,'ABHISHEK',99,18,'2016-12-11',1),
(13,'ROHAN',78,42,'2014-02-03',1),
(14,'VISHU',66,21,'2011-11-08',1),
(15,'SIMARPREET',78,17,'2011-03-04',1),
(16,'ARJUN',79,19,'2003-05-15',1),
(17,'shivam',89,28,'1999-12-11',1),
(18,'PRAVEEN',98,21,'2014-11-24',1),
(19,'hardik',33,24,'2009-12-03',1),
(20,’chahal',33,25,'2002-12-11',1);


**JAVA FRONT-END DRIVER CODE LINKED VIA JDBC:-**

import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.ResultSet;
import java.sql.Statement;
import java.util.Scanner;
import java.util.concurrent.TimeUnit;
import java.io.IOException;

public class ConnectionMySQL {

public static void main(String args[]) throws
IOException, InterruptedException {
Scanner sc = new Scanner(System.in);
while (true) {

System.out.println("\n\n\t\t\t\t------------------ICC CRICKET
ACADEMY------------" + "\n\n");
System.out.println("1. VIEW DETAILS" + "\n" +
"2. INSERT DETAILS\n" + "3. UPDATE DETAILS\n" + "4.Exit");
System.out.println("Enter your choice:");
int ch = sc.nextInt();

for (int i = 0; i < 1000; i++) {
System.out.println("\b");
}

switch (ch) {
case 1:
System.out.println("Want to view Details
of ??");
System.out.println("1. PLAYERS\n" + "2.
COACHES\n" + "3. TEAMS\n" + "4. SERIES RECORDS\n");
System.out.println("Enter your Choice :");
int ch2 = sc.nextInt();

for (int i = 0; i < 1000; i++) {
System.out.println("\b");
}
switch (ch2) {
case 1:


System.out.println("Enter the name of
Player to be viewed :");
String name;
Scanner tc = new Scanner(System.in);
name = tc.next();
name = name.toUpperCase();
try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false", "root",
"2173009489@gmail");
String query = "SELECT
PLAYER_ID,PLAYER.NAME,FITNESS,AGE,DEBUT,TEAMS.TEAM_ID,TEAMS.C
OUNTRY,HUNDREDS,FIFTIES,RUNS,BATSMAN.NO_OF_MATCHES,BATSMAN.RA
NK,WICKETS,"
+
"BOWLER.RANK,BOWLER.NO_OF_MATCHES,5_WICKETS,ECONOMY " + "FROM
PLAYER "
+ "INNER JOIN BATSMAN
ON PLAYER.PLAYER_ID = BATSMAN.ID "
+ "INNER JOIN BOWLER ON
PLAYER.PLAYER_ID = BOWLER.ID "
+ "INNER JOIN TEAMS ON
PLAYER.TEAM = TEAMS.TEAM_ID " + "WHERE PLAYER.NAME = '" +
name
+ "'";
Statement stmt =
conn.createStatement();
ResultSet rs =
stmt.executeQuery(query);
System.out.println("General Info
About " + name);

System.out.format("%10s%15s%17s%15s%15s%15s%15s", "Player
ID", "Name", "Fitness Score", "Age",
"Debut Date", "Team
ID", "Country");
System.out.println();

while (rs.next()) {

System.out.format("%10s%15s%17s%15s%15s%15s%15s",
rs.getString("PLAYER_ID"),

rs.getString("PLAYER.NAME"), rs.getString("FITNESS"),
rs.getString("AGE"),


rs.getString("DEBUT"), rs.getString("TEAMS.TEAM_ID"),

rs.getString("TEAMS.COUNTRY"));
}
System.out.println();
rs = stmt.executeQuery(query);
System.out.println(name + " as a
Batsman:- ");

System.out.format("%10s%15s%15s%17s%15s", "Rank", "Hundreds",
"Fifties", "Runs",
"No of Matches");
System.out.println();

while (rs.next()) {

System.out.format("%10s%15s%15s%17s%15s",
rs.getString("BATSMAN.RANK"),

rs.getString("HUNDREDS"), rs.getString("FIFTIES"),
rs.getString("RUNS"),

rs.getString("BATSMAN.NO_OF_MATCHES"));
}

System.out.println();
rs = stmt.executeQuery(query);
System.out.println(name + " as a
Bowler:- ");

System.out.format("%10s%15s%15s%17s%15s", "Rank", "Wickets",
"5 Wickets", "No of Matches",
"Economy");
System.out.println();

while (rs.next()) {

System.out.format("%10s%15s%15s%17s%15s",
rs.getString("BOWLER.RANK"),

rs.getString("WICKETS"), rs.getString("5_WICKETS"),

rs.getString("BOWLER.NO_OF_MATCHES"),
rs.getString("BOWLER.ECONOMY"));
}


System.out.println();

}

catch (Exception e) {
System.out.println("No Such
PLAYER Exists!!");
System.err.println(e);
}

break;

case 2:

System.out.println("1.Search By coach
Name\n2.Search By Country");
Scanner vs = new Scanner(System.in);
int coi = sc.nextInt();

switch (coi) {
case 1:
System.out.println("Enter Coach
Name:- ");
name = vs.next();
name = name.toUpperCase();

try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false",
"root",
"2173009489@gmail");
String query = "SELECT
COACH_ID, COACH.NAME,COACH.AGE,TEAMS.COUNTRY FROM COACH INNER
JOIN TEAMS ON COACH.TEAM = TEAMS.TEAM_ID WHERE COACH.NAME =
'"
+ name + "'";
Statement stmt =
conn.createStatement();
ResultSet rs =
stmt.executeQuery(query);

System.out.format("%10s%15s%17s%15s", "Coach ID", "Name",
"Age", "Country");
System.out.println();


while (rs.next()) {

System.out.format("%10s%15s%17s%15s",
rs.getString("COACH.COACH_ID"),

rs.getString("COACH.NAME"), rs.getString("COACH.AGE"),

rs.getString("TEAMS.COUNTRY"));
}
}

catch (Exception e) {
System.out.println("No Such
Coach Exists!!");
System.err.println(e);
}

break;

case 2:
System.out.println("Enter
Country:- ");
name = vs.next();
name = name.toUpperCase();
try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false",
"root",
"2173009489@gmail");
String query = "SELECT
COACH_ID, COACH.NAME,COACH.AGE,TEAMS.COUNTRY \n" + "FROM
COACH \n"
+ "INNER JOIN
TEAMS ON COACH.TEAM = TEAMS.TEAM_ID WHERE TEAMS.COUNTRY = '"
+ name
+ "'";
Statement stmt =
conn.createStatement();
ResultSet rs =
stmt.executeQuery(query);

System.out.format("%10s%15s%17s%15s", "Coach ID", "Name",
"Age", "Country");
System.out.println();


while (rs.next()) {

System.out.format("%10s%15s%17s%15s",
rs.getString("COACH.COACH_ID"),

rs.getString("COACH.NAME"), rs.getString("COACH.AGE"),

rs.getString("TEAMS.COUNTRY"));
}
}

catch (Exception e) {
System.out.println("No Such
Coach Exists!!");
System.err.println(e);
}

break;

}

break;

case 3:
System.out.println("Enter name of
Team whose details you want to see :");
String teamName;
teamName = sc.next();
try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false", "root",
"2173009489@gmail");

String query = "SELECT
TEAMS.TEAM_ID,TEAMS.COUNTRY,PLAYER.NAME AS
CAPTAIN,TEAMS.RANK,MANAGER.MANAGER_ID,MANAGER.NAME AS
MANAGER_NAME FROM TEAMS INNER "
+ "JOIN PLAYER ON
PLAYER.PLAYER_ID = TEAMS.CAPTAIN INNER JOIN "
+ "MANAGER ON
TEAMS.MANAGER_ID = MANAGER.MANAGER_ID WHERE TEAMS.COUNTRY =
'" + teamName
+ "'";


Statement stmt =
conn.createStatement();
ResultSet rs =
stmt.executeQuery(query);

System.out.format("%10s%15s%15s%15s%15s%15s", "Team ID",
"Country", "Captain", "Rank",
"Manager_ID", "Manager
Name");
System.out.println();

while (rs.next()) {

System.out.format("%10s%15s%15s%15s%15s%15s",
rs.getString("TEAMS.TEAM_ID"),

rs.getString("TEAMS.COUNTRY"), rs.getString("PLAYER.NAME"),

rs.getString("TEAMS.RANK"),
rs.getString("MANAGER.MANAGER_ID"),

rs.getString("MANAGER.NAME"));
}

}

catch (Exception e) {
System.out.println("No Such Team
Exists!!");
System.err.println(e);
continue;
}

break;

case 4:
System.out.println("Enter SERIES ID
of SERIES whose details you want to check :");

String seriesId = sc.next();
try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false", "root",
"2173009489@gmail");


String query = "SELECT
SERIES_ID,DURATION,FORMAT,PLAYER.NAME,TEAMS.COUNTRY\n" +
"FROM SERIES\n"
+ "INNER JOIN TEAMS ON
SERIES.WINNING_TEAM_ID = TEAMS.TEAM_ID \n"
+ "INNER JOIN PLAYER ON
SERIES.MAN_OF_THE_SERIES = PLAYER.PLAYER_ID\n"
+ "WHERE SERIES_ID = '"
+ seriesId + "'";

Statement stmt =
conn.createStatement();
ResultSet rs =
stmt.executeQuery(query);

System.out.format("%10s%13s%13s%19s%17s", "Series ID",
"Duration", "Format",
"Man Of The Series",
"Winning Team");
System.out.println();

while (rs.next()) {

System.out.format("%10s%13s%13s%19s%17s",
rs.getString("SERIES_ID"),

rs.getString("DURATION"), rs.getString("FORMAT"),
rs.getString("PLAYER.NAME"),

rs.getString("TEAMS.COUNTRY"));
}

}

catch (Exception e) {
System.out.println("No Such
Series Exists!!");
System.err.println(e);
continue;
}
System.out.println();

System.out.println("Want to view
Specific Match Details of this SERIES(0/1) ??");
int choice = sc.nextInt();


if (choice != 0) {
System.out.println("Enter Match
Id of Match whose details you want to view :");
int matchId = sc.nextInt();

try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false",
"root",
"2173009489@gmail");

String query = "SELECT
T1.COUNTRY AS TEAM_1, T2.COUNTRY AS TEAM_2,
SERIES.FORMAT,VENUE,T3.COUNTRY AS
WINNER_TEAM,DATE,MAN_OF_THE_MATCH\n"
+ "FROM MATCHES\n"
+ "INNER JOIN TEAMS AS T1 ON MATCHES.TEAM_1 = T1.TEAM_ID\n"
+ "INNER JOIN
TEAMS AS T2 ON MATCHES.TEAM_2 = T2.TEAM_ID\n"
+ "INNER JOIN
TEAMS AS T3 ON MATCHES.WINNER_TEAM = T3.TEAM_ID\n"
+ "INNER JOIN
SERIES ON MATCHES.SERIES_ID = SERIES.SERIES_ID\n"
+ "INNER JOIN
PLAYER ON MATCHES.MAN_OF_THE_MATCH = PLAYER.PLAYER_ID\n"
+ "WHERE MATCH_ID
= '" + matchId + "'";

Statement stmt =
conn.createStatement();
ResultSet rs =
stmt.executeQuery(query);

System.out.format("%10s%13s%13s%19s%17s%17s", "TEAM 1", "TEAM
2", "FORMAT", "WINNER TEAM",
"DATE", "MAN OF
THE MATCH");
System.out.println();

while (rs.next()) {

System.out.format("%10s%13s%13s%19s%15s%17s",
rs.getString("TEAM_1"),


rs.getString("TEAM_2"), rs.getString("FORMAT"),
rs.getString("WINNER_TEAM"),

rs.getString("DATE"), rs.getString("MAN_OF_THE_MATCH"));
}

}

catch (Exception e) {
System.out.println("No Such
Series Exists!!");
System.err.println(e);
continue;
}
System.out.println();

}

break;

default:
break;
}
break;

case 2:
System.out.println("What do you want to
Insert ?? ");
System.out.println("1. NEW PLAYER ?\n" +
"2. NEW COACH ?\n" + "3. NEW MANAGER ?\n");
System.out.println("Enter your Choice :");

ch2 = sc.nextInt();

for (int i = 0; i < 100; i++) {
System.out.println();
}

switch (ch2) {
case 1: {
System.out.println("General details:-
");
System.out.println("Enter Name:- ");
String name = sc.next();
System.out.println("Enter Age:- ");


String age = sc.next();
System.out.println("Enter Fitness
Score(out of 100):- ");
String fit = sc.next();

System.out.println("Enter Debut
Date:-");
String date = sc.next();
System.out.println("Enter Team ID:-
");
String team = sc.next();
System.out.println();

System.out.println("Batting Details:-
");
System.out.println("Hundreds:- ");
String hun = sc.next();
System.out.println("Fifties:-");
String fif = sc.next();
System.out.println("Runs:-");
String run = sc.next();
System.out.println("No of Matches:-
");
String m = sc.next();
System.out.println("Rank:- ");
String btr = sc.next();

System.out.println("Bowler Details:-
");
System.out.println("Enter Wickets:-
");
String wic = sc.next();
System.out.println("Enter Number of
matches:-");
String bm = sc.next();
System.out.println("Enter 5 Wickets:-
");
String five = sc.next();
System.out.println("Enter economy:-
");
String eco = sc.next();
System.out.println("Enter Rank:- ");
String bowr = sc.next();
try {


Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false", "root",
"2173009489@gmail");

String query1 = "INSERT INTO
PLAYER(NAME,AGE,FITNESS,DEBUT,TEAM)\n" + "VALUES (\'" + name
+ "\',\'" + age + "\',
\'" + fit + "\',\'" + date + "\',\'" + team + "\')\n";

String quer2 = "INSERT
INTO BATSMAN(HUNDREDS,FIFTIES,RUNS,NO_OF_MATCHES,RANK)\n" +
"VALUES (\'" + hun
+ "\',\'" + fif + "\',
\'" + run + "\',\'" + m + "\',\'" + btr + "\')";
String q3 = "INSERT
INTO BOWLER(ID,RANK,WICKETS,NO_OF_MATCHES,5_WICKETS,ECONOMY)
\n" + "VALUES(\'234\',"
+ bowr + "\',\'" + wic
+ "\',\'" + bm + "\',\'" + five + "\',\'" + eco + "\')";

Statement stmt1 =
conn.createStatement();
int rs1 =
stmt1.executeUpdate(query1);

Statement stmt2 =
conn.createStatement();
int rs2 =
stmt2.executeUpdate(quer2);

Statement stmt3 =
conn.createStatement();
int rs3 =
stmt3.executeUpdate(q3);
System.out.println();

}

catch (Exception e) {
System.out.println("Fail!!");
System.err.println(e);
continue;
}


break;
}

case 2: {
System.out.println("Enter Coach
Name:- ");
String name = sc.next();

System.out.println("Enter Team ID:-
");
String team = sc.next();
System.out.println("Enter Age:- ");
String age = sc.next();

try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false", "root",
"2173009489@gmail");

String query = "INSERT INTO
COACH(NAME,AGE,TEAM) VALUES(\"" + name + "\", \"" + age +
"\", \""
+ team + "\");";

Statement stmt =
conn.createStatement();
int rs =
stmt.executeUpdate(query);
System.out.println();

}

catch (Exception e) {
System.out.println("Fail!!");
System.err.println(e);
continue;
}

break;
}

case 3: {
System.out.println("Enter Manager
Name:- ");
String name = sc.next();


System.out.println("Enter Team ID:-
");
String team = sc.next();

try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false", "root",
"2173009489@gmail");

String query = "INSERT INTO
MANAGER(TEAM,NAME) VALUES (\"" + team + "\",\"" + name +
"\")";

Statement stmt =
conn.createStatement();
int rs =
stmt.executeUpdate(query);
System.out.println();

}

catch (Exception e) {
System.out.println("Fail!!");
System.err.println(e);
continue;
}

break;
}

}
break;
case 3:
System.out.println("Which existing Details
Do you want to Update ??");
System.out.println("1. PLAYER DETAILS?
\n2.Coach Details");
System.out.println("Enter your Choice :
");

ch2 = sc.nextInt();

switch (ch2) {


case 1:
System.out.println("Enter name of
PLAYER you would like to change :");
String name;
name = sc.next();

System.out.println("1.Update
Age\n2.Update Fitness");
int attr = sc.nextInt();

if (attr == 1) {
System.out.println("Enter new
age:- ");

int age = sc.nextInt();

try {
Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false",
"root",
"2173009489@gmail");

String query = "UPDATE
PLAYER SET AGE ='" + age + "' WHERE NAME ='" + name + "'";

Statement stmt =
conn.createStatement();
int rs =
stmt.executeUpdate(query);
System.out.println();

}

catch (Exception e) {

System.out.println("Fail!!");
System.err.println(e);
continue;
}

}

else {
int fit = sc.nextInt();
try {


Connection conn =
DriverManager.getConnection("jdbc:mysql://localhost/ICC?
useSSL=false",
"root",
"2173009489@gmail");

String query = "UPDATE
PLAYER SET FITNESS ='" + fit + "' WHERE NAME ='" + name +
"'";

Statement stmt =
conn.createStatement();
int rs =
stmt.executeUpdate(query);
System.out.println();

}

catch (Exception e) {

System.out.println("Fail!!");
System.err.println(e);
continue;
}

}

}

case 4: {
System.exit(0);
}

default:
System.out.println("Wrong Choice
Entered !!!!!");
// TimeUnit.SECONDS.sleep(1);
}

}
}
}


**SQL BACKEND DATABASE CODE:-**

#
************************************************************
# Sequel Pro SQL dump
# Version 4541
#
# [http://www.sequelpro.com/](http://www.sequelpro.com/)
# https://github.com/sequelpro/sequelpro
#
# Host: localhost (MySQL 5.7.20)
# Database: ICC
# Generation Time: 2017-11-08 19:13:36 +0000
#
************************************************************

/*!40101 SET @OLD_CHARACTER_SET_CLIENT=@@CHARACTER_SET_CLIENT
*/;
/*!40101 SET
@OLD_CHARACTER_SET_RESULTS=@@CHARACTER_SET_RESULTS */;
/*!40101 SET @OLD_COLLATION_CONNECTION=@@COLLATION_CONNECTION
*/;
/*!40101 SET NAMES utf8 */;
/*!40014 SET @OLD_FOREIGN_KEY_CHECKS=@@FOREIGN_KEY_CHECKS,
FOREIGN_KEY_CHECKS=0 */;
/*!40101 SET @OLD_SQL_MODE=@@SQL_MODE,
SQL_MODE='NO_AUTO_VALUE_ON_ZERO' */;
/*!40111 SET @OLD_SQL_NOTES=@@SQL_NOTES, SQL_NOTES=0 */;

# Dump of table BATSMAN
#
------------------------------------------------------------

DROP TABLE IF EXISTS `BATSMAN`;

CREATE TABLE `BATSMAN` (
`ID` int(11) NOT NULL AUTO_INCREMENT,
`HUNDREDS` int(11) NOT NULL DEFAULT '0',
`FIFTIES` int(11) NOT NULL DEFAULT '0',
`RUNS` int(11) NOT NULL DEFAULT '0',
`NO_OF_MATCHES` int(11) NOT NULL DEFAULT '0',
`RANK` int(11) NOT NULL DEFAULT '0',
PRIMARY KEY (`ID`),


CONSTRAINT `I` FOREIGN KEY (`ID`) REFERENCES `PLAYER`
(`PLAYER_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `BATSMAN` WRITE;
/*!40000 ALTER TABLE `BATSMAN` DISABLE KEYS */;

INSERT INTO `BATSMAN` (`ID`, `HUNDREDS`, `FIFTIES`, `RUNS`,
`NO_OF_MATCHES`, `RANK`)
VALUES
(1,12,65,4565,345,32),
(2,0,6,455,335,34),
(3,10,54,4425,344,35),
(4,78,633,4152,811,36),
(5,60,89,3214,465,39),
(6,3,54,5157,666,36),
(7,0,0,76,6,98),
(8,0,66,5422,189,38),
(9,33,654,6546,3444,22),
(10,21,13,890,67,5),
(11,33,87,565,454,55),
(12,0,0,0,0,89),
(13,0,0,23,11,90),
(14,327,984,85749,1000,1),
(15,1,2,422,5,80),
(16,0,0,76,43,101),
(17,0,5,877,9,99),
(18,40,12,543,33,3),
(19,33,22,23,23,2);

/*!40000 ALTER TABLE `BATSMAN` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table BOWLER
#
------------------------------------------------------------

DROP TABLE IF EXISTS `BOWLER`;

CREATE TABLE `BOWLER` (
`ID` int(11) NOT NULL,
`RANK` int(11) NOT NULL DEFAULT '0',
`WICKETS` int(11) NOT NULL DEFAULT '0',
`NO_OF_MATCHES` int(11) NOT NULL DEFAULT '0',
`5_WICKETS` int(11) NOT NULL DEFAULT '0',


`ECONOMY` int(11) NOT NULL DEFAULT '0',
KEY `PLAY` (`ID`),
CONSTRAINT `PLAY` FOREIGN KEY (`ID`) REFERENCES `PLAYER`
(`PLAYER_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `BOWLER` WRITE;
/*!40000 ALTER TABLE `BOWLER` DISABLE KEYS */;

INSERT INTO `BOWLER` (`ID`, `RANK`, `WICKETS`,
`NO_OF_MATCHES`, `5_WICKETS`, `ECONOMY`)
VALUES
(1,99,4,8,0,4),
(2,87,67,34,2,8),
(3,12,331,564,88,7),
(4,122,1,2,0,6),
(5,13,132,67,5,3),
(6,1,10,1,2,2),
(7,133,0,0,0,0),
(8,133,0,0,0,0),
(9,65,4,1,0,7),
(10,33,64,34,3,2),
(11,133,0,0,0,0),
(12,86,67,34,2,2),
(13,22,23,34,1,7),
(14,133,0,0,0,0),
(15,130,4,1,0,2),
(16,54,32,6,3,4),
(17,34,765,123,3,4);

/*!40000 ALTER TABLE `BOWLER` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table COACH
#
------------------------------------------------------------

DROP TABLE IF EXISTS `COACH`;

CREATE TABLE `COACH` (
`COACH_ID` int(11) NOT NULL AUTO_INCREMENT,
`TEAM` int(11) DEFAULT NULL,
`NAME` varchar(45) NOT NULL DEFAULT '',
`AGE` int(11) NOT NULL,
PRIMARY KEY (`COACH_ID`),


KEY `TEAM` (`TEAM`),
CONSTRAINT `coach_ibfk_1` FOREIGN KEY (`TEAM`) REFERENCES
`TEAMS` (`TEAM_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `COACH` WRITE;
/*!40000 ALTER TABLE `COACH` DISABLE KEYS */;

INSERT INTO `COACH` (`COACH_ID`, `TEAM`, `NAME`, `AGE`)
VALUES
(21,1,'CHARLES',43),
(22,2,'CRAIG',25),
(23,3,'DANIEL',27),
(24,4,'RAVI',32),
(25,5,'KAPIL',45),
(26,6,'SHIVAM',34),
(27,7,'SIMAR',36),
(28,8,'MESSI',31),
(29,NULL,'RONALDO',34),
(30,NULL,'GOTZE',29),
(31,NULL,'HRITHIK',44),
(32,3,'vishu',34),
(33,3,'yui',12);

/*!40000 ALTER TABLE `COACH` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table MANAGER
#
------------------------------------------------------------

DROP TABLE IF EXISTS `MANAGER`;

CREATE TABLE `MANAGER` (
`MANAGER_ID` int(11) NOT NULL AUTO_INCREMENT,
`TEAM` int(11) NOT NULL,
`NAME` varchar(45) NOT NULL DEFAULT '',
PRIMARY KEY (`MANAGER_ID`),
KEY `TM` (`TEAM`),
CONSTRAINT `TM` FOREIGN KEY (`TEAM`) REFERENCES `TEAMS`
(`TEAM_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `MANAGER` WRITE;
/*!40000 ALTER TABLE `MANAGER` DISABLE KEYS */;


INSERT INTO `MANAGER` (`MANAGER_ID`, `TEAM`, `NAME`)
VALUES
(11,1,'ANDREW'),
(12,2,'SMITH'),
(13,3,'GANGULY'),
(14,4,'GEORGE BUSH'),
(15,5,'OBAMA'),
(16,6,'LINCOLN'),
(17,7,'CLINTON'),
(18,8,'BILL GATES');

/*!40000 ALTER TABLE `MANAGER` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table MATCHES
#
------------------------------------------------------------

DROP TABLE IF EXISTS `MATCHES`;

CREATE TABLE `MATCHES` (
`MATCH_ID` int(11) NOT NULL AUTO_INCREMENT,
`TEAM_1` int(11) NOT NULL,
`TEAM_2` int(11) NOT NULL,
`SERIES_ID` int(11) NOT NULL,
`VENUE` varchar(45) NOT NULL DEFAULT '',
`WINNER_TEAM` int(11) NOT NULL,
`DATE` date NOT NULL,
`MAN_OF_THE_MATCH` int(11) NOT NULL,
PRIMARY KEY (`MATCH_ID`),
KEY `TM1` (`TEAM_1`),
KEY `TM2` (`TEAM_2`),
KEY `WN` (`WINNER_TEAM`),
KEY `MAN` (`MAN_OF_THE_MATCH`),
KEY `SID` (`SERIES_ID`),
CONSTRAINT `MAN` FOREIGN KEY (`MAN_OF_THE_MATCH`)
REFERENCES `PLAYER` (`PLAYER_ID`) ON DELETE CASCADE ON UPDATE
CASCADE,
CONSTRAINT `SID` FOREIGN KEY (`SERIES_ID`) REFERENCES
`SERIES` (`SERIES_ID`) ON DELETE CASCADE ON UPDATE CASCADE,
CONSTRAINT `TM1` FOREIGN KEY (`TEAM_1`) REFERENCES `TEAMS`
(`TEAM_ID`) ON DELETE CASCADE ON UPDATE CASCADE,
CONSTRAINT `TM2` FOREIGN KEY (`TEAM_2`) REFERENCES `TEAMS`
(`TEAM_ID`) ON DELETE CASCADE ON UPDATE CASCADE,


CONSTRAINT `WN` FOREIGN KEY (`WINNER_TEAM`) REFERENCES
`TEAMS` (`TEAM_ID`) ON DELETE CASCADE ON UPDATE CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `MATCHES` WRITE;
/*!40000 ALTER TABLE `MATCHES` DISABLE KEYS */;

INSERT INTO `MATCHES` (`MATCH_ID`, `TEAM_1`, `TEAM_2`,
`SERIES_ID`, `VENUE`, `WINNER_TEAM`, `DATE`,
`MAN_OF_THE_MATCH`)
VALUES
(81,4,2,42,'KOTLA',2,'2017-11-20',2),
(82,5,1,42,'KOTLA',1,'2017-04-11',17),
(83,2,8,42,'WANKHADE',8,'2017-04-12',15),
(84,3,6,42,'WANKHEDE',6,'2017-11-03',6),
(85,7,4,42,'KOTLA',4,'2017-12-08',11),
(88,8,1,43,'DHRMSHALA',1,'2016-04-09',1),
(89,4,8,43,'CHINNASWAMI',8,'2017-04-18',8);

/*!40000 ALTER TABLE `MATCHES` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table PLAYER
#
------------------------------------------------------------

DROP TABLE IF EXISTS `PLAYER`;

CREATE TABLE `PLAYER` (
`PLAYER_ID` int(11) NOT NULL AUTO_INCREMENT,
`NAME` varchar(45) NOT NULL DEFAULT '',
`FITNESS` int(11) NOT NULL,
`AGE` int(11) NOT NULL,
`DEBUT` date NOT NULL,
`TEAM` int(11) NOT NULL,
PRIMARY KEY (`PLAYER_ID`),
KEY `TEAM` (`TEAM`),
CONSTRAINT `player_ibfk_1` FOREIGN KEY (`TEAM`) REFERENCES
`TEAMS` (`TEAM_ID`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `PLAYER` WRITE;
/*!40000 ALTER TABLE `PLAYER` DISABLE KEYS */;


INSERT INTO `PLAYER` (`PLAYER_ID`, `NAME`, `FITNESS`, `AGE`,
`DEBUT`, `TEAM`)
VALUES
(1,'DHONI',89,31,'2007-11-12',1),
(2,'kohli',87,22,'2010-01-23',1),
(3,'rohit',78,32,'2001-08-30',1),
(4,'TENDULKAR',99,14,'1999-12-01',1),
(5,'RAHUL',78,30,'2002-09-05',1),
(6,'VIRAT',97,28,'2012-02-02',1),
(7,'dhawan',100,29,'2015-12-01',1),
(8,'ashwin',98,27,'2008-04-26',1),
(9,'bumrah',89,21,'2007-11-19',1),
(10,'ganguly',69,22,'2013-10-18',1),
(11,'GEETU',1,19,'2017-11-11',1),
(12,'ABHISHEK',99,18,'2016-12-11',1),
(13,'ROHAN',78,42,'2014-02-03',1),
(14,'VISHU',66,21,'2011-11-08',1),
(15,'SIMARPREET',78,17,'2011-03-04',1),
(16,'ARJUN',79,19,'2003-05-15',1),
(17,'shivam',89,28,'1999-12-11',1),
(18,'PRAVEEN',98,21,'2014-11-24',1),
(19,'hardik',33,24,'2009-12-03',1),
(20,'chahal',33,25,'2002-12-11',1);

/*!40000 ALTER TABLE `PLAYER` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table SERIES
#
------------------------------------------------------------

DROP TABLE IF EXISTS `SERIES`;

CREATE TABLE `SERIES` (
`SERIES_ID` int(11) NOT NULL,
`DURATION` int(11) NOT NULL,
`FORMAT` varchar(45) NOT NULL DEFAULT 'ONE DAY
INTERNATIONAL',
`WINNING_TEAM_ID` int(11) NOT NULL DEFAULT '0',
`MAN_OF_THE_SERIES` int(11) NOT NULL DEFAULT '0',
PRIMARY KEY (`SERIES_ID`),
KEY `WINNER` (`WINNING_TEAM_ID`),
KEY `MM` (`MAN_OF_THE_SERIES`),


CONSTRAINT `MM` FOREIGN KEY (`MAN_OF_THE_SERIES`)
REFERENCES `PLAYER` (`PLAYER_ID`) ON DELETE CASCADE ON UPDATE
CASCADE,
CONSTRAINT `WINNER` FOREIGN KEY (`WINNING_TEAM_ID`)
REFERENCES `TEAMS` (`TEAM_ID`) ON DELETE CASCADE ON UPDATE
CASCADE
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `SERIES` WRITE;
/*!40000 ALTER TABLE `SERIES` DISABLE KEYS */;

INSERT INTO `SERIES` (`SERIES_ID`, `DURATION`, `FORMAT`,
`WINNING_TEAM_ID`, `MAN_OF_THE_SERIES`)
VALUES
(42,5,'TEST',4,11),
(43,3,'ODI',1,1),
(44,5,'T20',6,14);

/*!40000 ALTER TABLE `SERIES` ENABLE KEYS */;
UNLOCK TABLES;

# Dump of table TEAMS
#
------------------------------------------------------------

DROP TABLE IF EXISTS `TEAMS`;

CREATE TABLE `TEAMS` (
`TEAM_ID` int(11) NOT NULL,
`COUNTRY` varchar(45) NOT NULL DEFAULT '',
`CAPTAIN` int(45) NOT NULL,
`RANK` int(11) NOT NULL DEFAULT '0',
`NO_OF_MATCHES` int(45) NOT NULL DEFAULT '0',
`MANAGER_ID` int(11) NOT NULL,
PRIMARY KEY (`TEAM_ID`),
KEY `CAPTAIN` (`CAPTAIN`),
KEY `MANGER ID` (`MANAGER_ID`),
CONSTRAINT `teams_ibfk_1` FOREIGN KEY (`CAPTAIN`)
REFERENCES `PLAYER` (`PLAYER_ID`) ON DELETE CASCADE ON UPDATE
CASCADE,
CONSTRAINT `teams_ibfk_2` FOREIGN KEY (`MANAGER_ID`)
REFERENCES `MANAGER` (`MANAGER_ID`)
) ENGINE=InnoDB DEFAULT CHARSET=latin1;

LOCK TABLES `TEAMS` WRITE;


/*!40000 ALTER TABLE `TEAMS` DISABLE KEYS */;

INSERT INTO `TEAMS` (`TEAM_ID`, `COUNTRY`, `CAPTAIN`, `RANK`,
`NO_OF_MATCHES`, `MANAGER_ID`)
VALUES
(1,'INDIA',1,12,877,11),
(2,'PAKISTAN',2,72,8734,12),
(3,'AUSTRALIA',3,42,123,13),
(4,'SOUTH AFRICA',4,22,73,14),
(5,'ENGLAND',5,90,763,15),
(6,'RUSSIA',6,88,746,16),
(7,'SPAIN',7,34,3545,17),
(8,'GERMANY',8,21,636,18);

/*!40000 ALTER TABLE `TEAMS` ENABLE KEYS */;
UNLOCK TABLES;


