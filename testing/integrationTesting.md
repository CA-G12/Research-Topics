## What is Integration Testing?

Integration Testing is defined as a type of testing where software modules are integrated logically and tested as a group. A typical software project consists of multiple software modules, coded by different programmers. The purpose of this level of testing is to expose defects in the interaction between these software modules when they are integrated

Integration Testing focuses on checking data communication amongst these modules. Hence it is also termed as ‘I & T’ (Integration and Testing), ‘String Testing’ and sometimes ‘Thread Testing’.

Although each software module is unit tested, defects still exist for various reasons like
    • A Module, in general, is designed by an individual software developer whose understanding and programming logic may differ from other programmers. Integration Testing becomes necessary to verify the software modules work in unity

    • At the time of module development, there are wide chances of change in requirements by the clients. These new requirements may not be unit tested and hence system integration Testing becomes necessary.

    • Interfaces of the software modules with the database could be erroneous

    • External Hardware interfaces, if any, could be erroneous

    • Inadequate exception handling could cause issues.

## Example of Integration Test Case

Integration Test Case differs from other test cases in the sense it focuses mainly on the interfaces & flow of data/information between the modules. Here priority is to be given for the integrating links rather than the unit functions which are already tested.
Sample Integration Test Cases for the following scenario: Application has 3 modules say ‘Login Page’, ‘Mailbox’ and ‘Delete emails’ and each of them is integrated logically.
Here do not concentrate much on the Login Page testing as it’s already been done in Unit Testing. But check how it’s linked to the Mail Box Page.
Similarly Mail Box: Check its integration to the Delete Mails Module.

## Types of Integration Testing

Software Engineering defines variety of strategies to execute Integration testing, viz.
    •  Big Bang Approach :

    •  Incremental Approach: which is further divided into the following

        ◦  Top Down Approach

        ◦  Bottom Up Approach

        ◦  Sandwich Approach – Combination of Top Down and Bottom Up
Below are the different strategies, the way they are executed and their limitations as well advantages.
Big Bang Testing

Big Bang Testing is an Integration testing approach in which all the components or modules are integrated together at once and then tested as a unit. This combined set of components is considered as an entity while testing. If all of the components in the unit are not completed, the integration process will not execute.

## Advantages

    • Convenient for small systems.
Disadvantages:
    • Fault Localization is difficult.

    • Given the sheer number of interfaces that need to be tested in this approach, some interfaces link to be tested could be missed easily.

    • Since the Integration testing can commence only after “all” the modules are designed, the testing team will have less time for execution in the testing phase.

    • Since all modules are tested at once, high-risk critical modules are not isolated and tested on priority. Peripheral modules which deal with user interfaces are also not isolated and tested on priority.
