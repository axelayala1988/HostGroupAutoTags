# Dynatrace Auto-Tags based on Host Groups
## Program to create tags in Dynatrace based on Host Group naming conventions

# How to use
Before running the executable, make sure you install the required module
```
pip install -r prerequisites.txt
```
You will also need Python installed on your local to be able to use it.

# Considerations
There are some xonsiderations to keep in mind to use this program:

1.  Keep it simple. Out of the box, you can only specify host group naming conventions of up to 4 parameters at most. Here are some exmaples of the permitted naming conventions:
  ```
  Application
  Application_Environment
  Application_Tier_Environment
  Application_Tier_Environment_DataCenter
  ```
2.  Use underscores (_) to separate parameters.
3.  You can't repeat naming convention patterns.
    - For example, if you define a naming convention like this:
    ```
    Application_Environment
    ```
    is a similar pattern as the following:
    ```
    Component_BusinessUnit
    ```
    You would need to either increase/decrease the number of parameters in your naming conventions without exceeeding the limit (4)
4.  Pass only the tenant identifier (xyz12345.live.dynatrace.com) or the cluster id and environment (n01.ydm947.dynatrace-managed.com/e/606c6d76-6695-4487-ba5c-fafdfd6e278b), without slashes (/)
5.  The API Token needs both read and write configuration permitions.
