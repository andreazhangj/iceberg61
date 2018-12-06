We decided to implement a friends feature to limit the number of
student's locations a user can see. There were two main reasons:
privacy and readability. An app that can allow you to see anyone's
table number, not just people you were friends with, could make
users uncomfortable. By limiting the scope of users' knowledge,
we protect other users' privacy. Additionally, there are hundreds
of people in Annenberg at once. Even if a fraction of the people used
Iceberg, users would have a difficult time scrolling through to find
people they are interested in sitting with.

We also wanted to delete a user's table number after half an hour.
People typically eat for less time than that, so we would not want
a user looking for a friend who had already left. To add a time
constraint, we got the current time and compared it to the time the
user arrived. After converting the times to six digit integers
(2 for hour, 2 for minute, 2 for second), we took the difference.
Then, we needed a little math. If the hour was the same, we looked
for a difference greater than 30 minutes to erase the table. But if the
hour was different, we looked for a difference greater than 70 minutes,
since time skips from 11:59 to 12:00, which would be 115900 to 120000, a
difference of 41 "minutes" instead of 1 real minute in our clock numbering'
system. Thus, we used 70 "minutes", 40 minutes greater than the normal
30 minutes.