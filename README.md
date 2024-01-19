CS210 Course Project - Ahmet Coşkun
#


This is a program that generates the most frequently used Turkish words by a single person in a WhatsApp chat using the .txt file of a chat exported from WhatsApp.

How the algorithm works:

Firstly, the user must create a .txt file where each line contains the path to the WhatsApp chats that the user wants to use and copy that .txt file’s path into the “file_path” variable. After this, the program processes each chatlog whose path is given in the .txt file, where it starts a loop for each line of the chatlog. 

At each iteration, the program searches for the name of the person who we are gathering the data of, and if their name is found, a series of preprocessing operations are conducted for the person’s text message. The program turns the message into lowercase and tokenizes each word by creating a list that contains the words in the message via the .split() function. Also, using functions from “Zeyrek” and “Zemberek-NLP” libraries, the program lemmatizes and normalizes each word. 

•To briefly explain the “normalize” function, in this program it is basically used to convert colloquial usages of Turkish words to their formal forms, e.g. “yapcan” to “yapacaksın”. 

Lastly, each word gets inserted to a dictionary that contains the words and how many times they have been encountered so far in the program. Once the entire process is over, we now have a dictionary containing how many times each word has been said by the person in the given WhatsApp chatlogs. 

The program then sorts the words by their occurrence counts and generates a bar chart of the top 25 most frequently used words by the person. Since this data is very likely to be made entirely of prepositions, conjunctions and words that do not mean anything by themselves, the program now conducts a stopword removal in the dictionary in order to find the words that give insight about the content of the person’s text messages. The stopword list is asked from the user in a .txt file where each line contains one stopword. Once the process is complete, another bar chart of the same fashion is generated, the only difference being the absence of the stopwords.
