# 7. Variables

## Variables

- repository
    
    are created by the OBIEE Administrator as part of the metadata repository.
    
    - Values of repository variables are reset on a regularly scheduled basis, and cannot be changed by any user.
    - The value of variable is the same for all users.
- Session
    
    are also created by the OBIEE Administrator as part of the metadata repository.
    
    - The values of session variables are established when a user logs in to OBIEE.
    - The same session variable may have a different value for each user.
    - System session variables:
        - These variables are not eligible to be changed by any user.
        - User ID, the user’s data security groups, and the user’s web catalog group(s) are all examples of system session variables.
    - Non-system session variables: These are variables which are defined by the OBIEE administrator.
        - The admin may allow users to change the values
        - populating such system variables can only be accomplished with a dashboard prompt.
    
- Presentation
    
    created by, and exist only in the context of, a Dashboard Prompt
    

## Example

![Untitled](7%20Variables/Untitled.png)

Work type is in Col 2 Lower limit is in Col 3

→ That’s why there is new column

## Prompt options

- Operator
    
    There are many different operators to choose from. While is equal to / is in is the most frequently used, some of the other commonly used values include:
    
    - is not equal to / is not in; • is greater than • is less than • is between • contains
- User Input
    
    The type of selection mechanism. There are five options available:
    
    - Choice List: A simple dropdown list of values to choose from. • Text Field: The user types a selection into the field
    - Check Boxes: The user can select one or more values from a list of check boxes.
    - Radio Buttons: The user can select one value from a radio button list.
    - List Box: Similar to the Choice List, except that the available values are shown on the left side of a selection dialog, and the selected values are shown on the right.
- Values
    
    Which values are displayed to the user? Some of the options here include:
    
    - All Column Values – display all values of the specified column
    - Specific Column Values – display only specifically named values of the column
    - SQL Results – display only those values returned as the result of a logical SQL statement. For example, the SQL statement select “Org”.”Work Type” from Training where “Effort”.”Corrected Hours” > 500 would return a limited set of Work Types for display in the prompt
- Limit values by
    
    This option allows us to display only relevant values of some prompts based on other prompts
    

## Default selection

There are five possible options for the Default to condition:

- None: No default is specified.
- Specific Value: A specified, hard-coded value.
- All Column Values: This option is only available when the Include “All Choices” choice in
the list option is selected. Select this option to specify the “All Choices” default value for the
prompt.
- Server Variable: The value of a Repository Variable or Session Variable will be the default.
For a session variable, prefix the name with NQ_SESSION, such as NQ_SESSION.USER.
- SQL Results: The results of a SQL statement.
- Variable Expression: references to reserved (system) session variables, including:
o @{system.currentTime}
o @{system.productVersion}
o @{session.locale}
o @{session.language}
o @{session.loginTime}
o @{session.logoutTime}
o @{session.lastAccessTime}
o @{[session.currentUser.id](http://session.currentuser.id/)}
o @{user.homeDirectory}
o @{[user.id](http://user.id/)}
o @{user.displayName}

## Set a Variable

The two possible values are Presentation Variable and Request Variable
• Presentation Variable: A variable that is created by the dashboard prompt
• Request Variable: The name of a Session Variable

## Drilling and Navigation

- Drill Link
    
    displays the next lowest hierarchical level of information (by default applied)
    
- Navigation Link
    
    redirects the user to a specified dashboard page or to a specified
    Answers analysis
    

> drill and navigation can act on heading and values
> 
- Heading Link
    
    The column header is presented as a link.
    
    - When used as a drill link, the "child" column is added to the analysis, and all existing
    values of the source column are retained (i.e. no filter is applied).
    - When used as a navigation link, clicking the heading link will open a specified Answers
    analysis or navigate to a specified dashboard page.
- Value Link
    
    The data values in a column are presented as links.
    
    - When used as a Drill Link, the "child" column is added to the analysis, and a filter
    condition is added to the analysis, limiting the "parent" column to only the value clicked.
    
    > For example, clicking on a value like Q1-2002 in the Quarter column will add the Month column to the analysis, will add a filter like "Quarter = Q1-2002", and will display only that quarter and the months related to it.
    > 
    - When used as a navigation link, Answers will open a specified Answers analysis or
    navigate to a specified dashboard page.
- clicking to drill on a column heading will retain all values in all columns, and just add
a new “child” column to the analysis (i.e. will not add filters),
- while clicking to drill on a value within a column will add a new “child” column and create filters for all columns to the left of the clicked cell

> example let’s take control over what happens when the user clicks on a column heading or a value
> 
- ex
    
    choose Action links
    
    ![Untitled](7%20Variables/Untitled%201.png)
    
    you have two options
    
    - add an existing analysis or dashboard
        
        ![Untitled](7%20Variables/Untitled%202.png)
        
        - Notes:
            - If an **Analysis** is specified as the destination that Analysis will be opened when the link is clicked.
                - if an analysis has an **is prompted** filter for the column. A navigation link can also serve as a filtering device when the target contains an **is prompted** filter for the column in question.
            - If a **Dashboard Page** is specified as the destination, the Dashboard will be displayed, and the specified Dashboard Page will be selected and visible, when the link is clicked
            - If a **Dashboard Name** is specified as the destination, the first page of the Dashboard will be displayed.
    - new function
        
        ![Untitled](7%20Variables/Untitled%203.png)
        
    
    result
    
    ![Untitled](7%20Variables/Untitled%204.png)