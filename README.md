# project-plan-template


Meta University Eng Project Plan Template     


AdoptHive (Web App)

Intern: Iyanuoluwa Fagbamila
Intern Manager: Robin Tan
Intern Director: Clare Yip
Peer(s): Alice Yang, Mark Hopson
GitHub Repository Link: https://github.com/Iyanuoluwa-abolade/project-plan-template

Overview

My project is an adoption webApp where potential parents are matched with orphans through orphanage staff/nuns.

Category:  Social Networking
Story: The adoption web app aims to connect prospective adoptive parents with orphanage staff/ nuns managing children’s profiles. The web app facilitates the adoption process by providing a platform for browsing profiles, expressing interest, managing documentation, and facilitating communication between parties involved in adoption.
Market: Individuals and families interested in adoption, as well as orphanages, nuns, and staff involved in child welfare. 
Habit:  Users engage with the platform to browse updated profiles of children, express interest, communicate with orphanage staff, upload and manage adoption-related documents 
Scope: The scope of the adoption web app includes features like detailed child profiles with multimedia content (photos, videos), and communication tools for interaction between parents and orphanage staff


Product Spec

User Stories

  
Required
As a parent, I want to browse profiles of children available for adoption, so that I can find a child whose profile matches my adoption criteria.
As a parent, I want to express interest in a specific child's profile, so that I can initiate the adoption process and communicate with the orphanage/nuns.
As a nun/orphanage staff member, I want to upload multimedia content such as photos and videos to children's profiles, so that potential parents can gain a deeper understanding of each child's personality and interests.
As a nun/orphanage staff member, I want to communicate with approved parents through the platform to schedule meetings or interviews, so that we can facilitate the adoption process effectively.
As a nun/orphanage staff member, I want to manage and update profiles of children available for adoption on the platform, so that potential parents can access accurate information.


Optional
As a parent, I want to receive guidance and support materials through the platform, such as FAQs and adoption guides, to assist me in navigating the adoption journey.
As a nun/orphanage staff member, I want to communicate with approved parents through the platform to schedule meetings or interviews, so that we can facilitate the adoption process effectively.
As a parent, I want to participate in virtual meetings or webinars organized by the orphanage/nuns, so that I can learn more about the adoption process and child care.
As a parent, I want to receive notifications about updates on children I've expressed interest in, such as new photos or progress reports, so that I can stay informed throughout the adoption process.
As a nun/orphanage staff member, I want to receive notifications about new parent applications and expressions of interest in children, so that I can promptly respond and manage inquiries.
As a nun/orphanage staff member, I want to gather feedback from parents about their adoption experience through the platform, so that we can continuously improve our services and support for families.

User Personas
Parents and Orphanage Staffs/Nuns

Motivation
Parents - Their motivation for using this app is to adopt children.
Orphanage Staffs/Nuns - Their motivation for using this app is to create a home for orphaned children

Adoption web app:
User can sign up
User can log in where they can see a list of profiles
User can express interest on a child’s profile
User can update profile information such as contact details, adoption preferences, and upload required documents
Nuns or orphanage can approve or reject applications
User password are encrypted in database
Website has clean and intuitive navigation interface

A brief introduction into the web app features:
- Parents fill out detailed questionnaires about their lifestyle and adoption preferences
- Children's profiles include multimedia content such as videos showcasing their personality, talents, and daily activities
- Parents receive notifications when there are updates on children they've expressed interest in, such as new photos or progress reports
- The platform offers a secure document management system where parents can upload and share adoption-related documents with the orphanage/nuns


Screen Archetypes:

Login Page
Create Account
Homepage/ Dashboard (Orphan profiles list/grid view)
Orphan profile details
Notification and updates
Chats

WireFrame

![Wireframe](https://github.com/Iyanuoluwa-abolade/project-plan-template/assets/152572720/fe147fb9-7081-4d98-bbb0-93954e30d307)


Data Model:

Orphan
ID
First name
Last name
Description
Gender
Birth date
Health Status
List of images/videos
Adoption Status

Potential adopter:
ID
First name
Last name
Phone number
Email
Address
Adoption Preferences

Orphanage Staff member/Nun:
ID
First name
Last name
Email
Phone number
Role
List of potential parents with whom they will be serving
List of orphan up for adoption


Server Endpoints

REST API

For Orphanage Staff Member/Nuns:

Create staff member/nuns profile (POST/staff_member_profile {staff ID})
Create orphans profile (POST /create_orphan_profile {first name} {last name} list<{media url}>)
Update orphans profile (PUT /update_orphan_profile {dict of update info})
Schedule meeting with adopter (POST /accept_adopter {adopter ID})
Manage documents for orphans (POST/orphan_document)

For Adopter:

Create Profile (POST/create_profile)
Update Profile (PUT/update_profile)
Express interest in orphan(POST/update_pofile)

Navigation

For Adoptive parents:

Upon successful registration, users are directed to their adopter profile dashboard or homepage.
From the dashboard or homepage, users access a list or grid view of orphan profiles with basic information and multimedia content.
A button or link on each orphan profile allows users to express interest, potentially triggering a confirmation message or notification.
Navigation includes sections for managing meetings, uploading documents securely, and viewing communication history with orphanage staff.

For Orphanage staffs/nuns:

Updating orphan profiles and uploading multimedia content,there is a dashboard where staff can view and edit orphan profiles, upload new content, and manage adoption status.
A section for managing adopter applications, scheduling meetings, and logging communication.


Technical Challenges

Technical Challenge #1 - Ranking/Matching algorithm

What:
Using a ranking or matching algorithm like Gale-Shapley to create matches between adopters and orphans.

How:
We will write a custom ranking/matching algorithm on the backend that matches adopters with orphans given the orphan’s preferences and the adopter’s preferences.

Technical Challenge #2 - Caching to improve latency of media extraction

What:
Since this is an app that heavily uses media (images, video) for profiles, we can use a CDN or some cache to speed up pulling the images.

How:
Use a CDN - When media files of the orphans or documents are first requested, the CDN fetches them from the origin server (where the files are stored like cloud storage or application server). https://www.cloudflare.com/

Database Integration

We can use MongoDB.

External APIs

SendGrid API to send email notifications to parents, adopters, and staff members.

Authentication

JWT-Based Authentication - A token based authentication

User authentication is managed using JWT-based authentication. When users sign up, their credentials are securely hashed and stored in our database. Upon logging in, the server issues a JWT containing encrypted user information and permissions, which is stored securely on the client side, typically as an HttpOnly and Secure cookie. This token allows seamless navigation between different screens by the same user, as each screen validates the JWT to determine access rights without relying on server-side sessions.

Visuals and Interactions

- Responsive Design
- Clean Interface
- Consistent Design Elements
- Visual Hierarchy
- Accessible Design
- Intuitive Navigation
- Interactive Elements
- Mobile-Friendly Interactions
- Interesting Cursor Interaction
- UI Component with Custom Visual Styling
- Loading State





