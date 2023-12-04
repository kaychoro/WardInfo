# WardInfo

I’d like a Flutter app that will work with a C# back-end server for creating agendas for weekly church meetings. I expect data to be stored in the back-end server and retrieved from the application using a REST API using role-based authentication. The application is for multiple congregations meeting in separate locations. Each congregation will have various roles. For a single congregation, this application is for attendees in the meeting and leaders of the meeting to build and publish a program agenda. The application contains the following roles: “congregation authority”, “administrator”, “leader”, “editor”, “authenticated user”, and “unauthenticated user”. The congregation authority role is only to create, modify, and delete congregations and assign administrators to that congregation. Administrators, leaders, and editors are assigned to a specific congregation and should be able to create a new program agenda or copy a prior week’s program agenda. The new and copied program agendas should start in the unpublished state and require an administrator, leader, or editor to publish them before making them visible to authenticated and unauthenticated users.

All users should be able search for a congregation by congregation name. Authenticated users, editors, leaders, and administrators should be able to mark multiple congregations as favorites so that they can quickly navigate back to that congregation.

A program agenda consists of the following elements:
- Name of the person Conducting
- Name of the person Presiding
- Name of the person being the Chorister
- Name of the person being the Organist or Pianist
- Heading for “Welcome and Announcements”
- Opening Hymn with number and name of the hymn
- Name of the person giving the Invocation
- Optional heading for “Ward Business”
- Optional section for business items:
	- Will have zero to many business items
	- Business items will have a type, name, and optional position
	- Business items may be the following types: “New Record”, “Calling Release”, “Calling Sustaining”, “Baby Blessing”, “Priesthood Ordination”, “Baptism”, or “Confirmation”
	- Business items are grouped by type
- Optional heading for Stake Business
- Sacrament Hymn with number and name of the hymn
- Heading for Administration of the Sacrament
- Optional section for program items:
- Will have zero to many program items
- Program items may be the following types: “Speaker”, “Hymn”, “Intermediate Hymn”, or “Testimony”
	- “Speaker” item will have a name of the speaker listed
	- “Hymn” will have the number and name of the hymn
	- “Intermediate Hymn” will have the number and name of the hymn
	- “Testimony” will have a name of the person giving their testimony
- Optional heading for Bearing of Testimonies
- Closing Hymn with number and name of the hymn
- Name of the person giving the Benediction
- Separate section for announcement items
	- Will have zero to many announcement items
	- Each announcement item will have a title, description, optional single picture, and optional expiration date
	- Announcement item descriptions should allow rich text editing
	- Announcement items should be ordered by the user

Roles:
1. Unauthenticated users should be able to see the program elements with the following exceptions:
a. Hide all names except name of the person Conducting and name of the person Presiding
b. Only show the title for each announcement item, unless it is marked as public
c. May not see any Business items
2. Authenticated user should be able see the program elements with the following exceptions:
	a. May not see any Business items
3. Authenticated editors should be able to create new programs and see and edit the program elements with the following exceptions:
	a. May not see or edit any Business items
4. Authenticated leaders should be able to create new programs and see and edit all program elements
5. Authenticated administrators should be able to assign different roles to all users, create new programs, and see and edit all program elements

There should be 3 different views for a single program:
1. Editor view: view for editor, leader, or administrator to re-order and edit all program elements
2. Conducting view: view for a leader or administrator follow the program for conducting the meeting; should intersperse the different sections of program elements with customizable text for transitions between parts of the meeting
3. Program view: default view for all users which shows all program elements visible to the user


Announcements should be easy to copy from one agenda to the next
![image](https://github.com/kaychoro/WardInfo/assets/2902618/a92f6117-377e-4c10-956e-09380be418dc)
