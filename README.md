# SQL Excercise 09
Exercise from ADAT
 Exercise 9
Under ORACLE, SET AUTOCOMMIT ON performs a COMMIT after each SQL statement. This setting is to be switched off for the following exercises with SET AUTOCOMMIT OFF. Note that a transaction end must then be explicitly executed by the COMMIT command.
Perform the following exercises in teams of 2!
1. create a table TEST, give your exercise partner all rights on this table and insert records together.
2. try to create a deadlock and see how the system reacts to it.
3. person A changes a record. Determine at what point in time this change is available to person B. 4.
4. perform the following processing:
<table>
  <tr><th>User A</th><th>User B</th></tr>
  <tr>
    <td>read record A</td>
    <td>performs the same action
  In addition, one field of this record is changed</td>
  </tr>
  <tr>
    <td></td>
    <td>
      end transaction B
    </td>
  </tr>
    <tr>
    <td>change record A
    end transaction A
   </td>
    <td>
   </td>
  </tr>
</table>
a) Is this processing sequence feasible?

b) Modify the example so that User B changes another record. Consider-
what locking mechanisms does Oracle use? 

5) Determine how the system reacts when both transactions insert the same record (with and without PRIMARY KEY).

6. reproduce the following situation: 
<table>
  <tr><th>User A</th><th>User B</th></tr>
  <tr>
    <td>update any record </td>
    <td></td>
  </tr>
  <tr>
    <td></td>
    <td>
    change this record
    </td>
  </tr>
    <tr>
    <td>
    ROLLBACK
   </td>
    <td>
   </td>
  </tr>
      <tr>
    <td>
   </td>
    <td>
    COMMIT
   </td>
  </tr>
      <tr>
    <td>read Record C
   </td>
    <td>
   </td>
  </tr>
      <tr>
    <td>
   </td>
    <td>
    COMMIT
   </td>
  </tr>
</table>

 7. simulate the Inconsistent Analysis Problem!
<table>
  <tr><th>User A</th><th>User B</th></tr>
  <tr>
    <td>Read record A</td>
    <td></td>
  </tr>
  <tr>
   <td>
    </td>
    <td>Update record C</td>
    
  </tr>
    <tr>
    <td>read record B
   </td>
    <td>
   </td>
  </tr>
      <tr>
    <td>
   </td>
    <td>
    Update record A
   </td>
  </tr>
      <tr>
    <td>read Record C
   </td>
    <td>
   </td>
  </tr>
      <tr>
    <td>
   </td>
    <td>
    COMMIT
   </td>
  </tr>
</table>
Modify the example in such a way that for user A the condition of the data sets A, B and C of a certain time is indicated!

8.
- User A selects a dataset according to a certain criterion.

- User B changes the criterion according to which the selection was made.

- User A changes a value in the previously selected data set.

What happens? What could be done so that between selection and change exactly this selected record cannot be changed by another user?

9.
- User B creates a table with a foreign key that references User A's table.
- User A should now revoke the right that user B can set a reference to his table.
Which values can user B insert in the foreign key column afterwards?
