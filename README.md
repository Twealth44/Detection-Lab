# Managed access permissions

## Objective
[This project involves adding a new employee to a group, moving them to a secondary group while keeping them in their primary group, and deleting their access from the system after one year with the company.]

- A new employee has joined the Research department. In this task, we want to add them to the system. The userid is researcher9. Uisng the command 👉🏻  [sudo useradd researcher9]

  ![Image 4-13-24 at 10 45 AM](https://github.com/Twealth44/Detection-Lab/assets/166849853/edae5e18-d37c-4ccf-9b5b-8307f5f009c3)
  
- Now, we also want to add them to a group in the organisation called "Research_team".
  Using the command 👉🏻 [sudo usermod -g research_team researcher9]

![2](https://github.com/Twealth44/Detection-Lab/assets/166849853/780d3395-b65d-40b9-9da0-bee12e0903c6)

Here you see the command line: sudo useradd -g research_team researcher9
(Sudo temporarily grant elevated permission to a specific users. -g is a command to assign thr group the user will belong)
Nb: (the group comes first before the user’s name)

- We want to assign file ownership. Researcher9 will be responsible for that. Presently, researcher2 is the one managing the file. The file name is project_r.txt. Using the command 👉🏻 [sudo chown researcher9 /home/researchr2/project_r.txt]
![3](https://github.com/Twealth44/Detection-Lab/assets/166849853/eaf7d9ab-5f39-4481-b9f2-2bcac9396616)


- We are about to add the user to a secondary group after a couple of months . They are going to be working in both the Research and Sales departments. The secondary group is sales team and their primary group is research team. Usng the command 👉🏻 [sudo usermod -a -G sales_team researcher9].
  ![4](https://github.com/Twealth44/Detection-Lab/assets/166849853/a85e114f-ac58-4aab-a624-9b21ee3fba5c)

- (-a is to append the user to a new or secondary group without leaving their primary group)
(-G is the command for identifying secondary group followed by the name of the group they are being added to)
(The user’s name followed- who we are adding to this group)

- A year later, reseacher9 decides to leave the company. The task is to remove them from the system. Uisng the command 👉🏻 [sudo userdel researcher9].
  ![5](https://github.com/Twealth44/Detection-Lab/assets/166849853/74f84103-f768-4b40-9144-03f9a9402864)

Note: When you create a new user in Linux, a group is automatically generated with the same name as the user, and the user becomes the sole member of that group. After deleting users, it is advisable to remove any empty groups that might be left behind. This is why the second line includes the command "groupdel."👉🏻  [sudo groupdel researcher9]
![6](https://github.com/Twealth44/Detection-Lab/assets/166849853/21459320-d04f-428d-b902-db970a85296b)



### Skills Learned
- Ability to use Linux to add, remove, move new employees within groups.
- Ability to change permissions among users based on their roles
- Advanced understanding of Linux and practical application.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used
-Linux

Key Learnings: Managing employee access permissions is a critical aspect of maintaining security and compliance. This project highlighted the importance of regularly reviewing and updating permissions to align with employees' roles and tenure with the company.

Impact:The project improved the organization's security posture by ensuring that employee access permissions were appropriately managed throughout their tenure, reducing the risk of unauthorized access and data breaches.

Future Plans: Implementing an automated system for managing employee access permissions could streamline the process and ensure that permissions are updated in a timely manner. Additionally, conducting regular audits of employee access permissions can help identify and mitigate any potential security risks.
