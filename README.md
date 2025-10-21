Career4All – AI-Powered Career Coaching Application

Built on Amazon Q Business by Dr. Lamia Ghozy
________________________________________
🚀 Project Overview

The Career4All Coaching Application automates the manual career coaching process by leveraging Amazon Q Business — AWS’s no-code, AI-driven platform.
The solution enables Career Coaches to upload learner CVs and job descriptions, perform automated skill-gap analysis, and generate personalized training recommendations from internal and external course catalogs.
It replaces hours of manual review with instant, data-driven insights — improving scalability, accuracy, and consistency across the organization.
________________________________________
🏢 Business Context

Career4All is a professional development platform that connects learners with certified coaches. The company faced critical operational bottlenecks:

•	Time-consuming manual skill analysis
•	Inconsistent training recommendations
•	Difficulty keeping training resources up-to-date

This application was built to solve those issues — automating the full cycle from resume review → gap analysis → training recommendations → schedule generation, while keeping access secure and compliant.
________________________________________
⚙️ Solution Architecture

Core AWS Services Used

•	Amazon Q Business – Application framework, UI, and AI logic
•	Amazon S3 – Dynamic data source for training catalogs (coaching-catalogues bucket)
•	IAM Identity Center – User authentication and access management
•	Access Control Lists (ACL) – Enforcing restricted content visibility
•	Global Controls – Keyword moderation and filtering

Functional Layers

1.	Frontend Layer: Q App UI with multiple input/output cards.
2.	Data Layer: Static PDFs and S3 dynamic catalogues.
3.	Logic Layer: Skill-gap analysis, course mapping, and scheduling logic.
4.	Security Layer: ACLs + keyword filters.
5.	Integration Layer: Automated sync for new S3 uploads.
________________________________________
🧩 Application Components

Input Cards

Card Type	                  Purpose
Upload CV (File Input):	Allows learners to upload their resumes.
Paste CV (Text Input):	Enables manual CV text entry.
Upload Job Description (File Input):	Accepts employer or job profile.
Paste Job Description (Text Input):	Allows job text entry for analysis.
Udacity Course Catalog Upload:	Adds static training PDFs.
________________________________________
Output Cards

Card Name	             Function

Skill Gap Analysis:	Identifies missing competencies.
Matching Skill Sets:	Lists existing learner skills.
Missing Skill Sets:	Lists missing learner skills.
Coach Recommendations:	Allows natural-language refinement by coaches.
Learning Schedule:	Auto-generates an optimised timeline.
________________________________________
📦 Data Integration

1. Static Source

•	PDF training catalogue manually uploaded from Career4All’s repository.

2. Dynamic Source

•	Amazon S3 Bucket: coaching-catalogues
o	Subfolder: /medicine
o	Contains multiple PDF training files.
o	Configured with daily automatic sync to ensure the latest training materials are available.
✅ Verification: Confirmed sync time visible in the Q App Data Sources tab.
________________________________________
🔐 Security and Access Control

CareerCoaches Group

User	              Role

career.coach.one	Senior Career Coach
career.coach.two	Assistant Coaches
•	Configured in IAM Identity Center.
•	An ACL file was uploaded and applied to restrict certain course documents.
•	Validation: authorised users can access restricted content; others are denied.
📁 File: career4all_acl.json
________________________________________
🚫 Content Moderation

Implemented Global Keyword Filtering in Amazon Q Business:

•	Blocked keywords: Gambling, Casino, and related terms.
•	Ensures content integrity, professional compliance, and platform safety.
________________________________________
🧑💻 User Guide

1. Using the Application

1.	Open the Amazon Q Business application: Career4All Coaching App.
2.	Upload or paste a CV and Job Description.
3.	Click Run Analysis to generate:
o	Skill Gap
o	Matching Skills
o	Course Recommendations
o	Suggested Schedule
4.	(Optional) Coaches can refine results by typing natural language inputs such as:
“Focus on cloud computing and data analytics”
“Recommend beginner-level programs only”

2. Updating Data Sources

•	Upload new course PDFs into the S3 bucket under /coaching-catalogues/.
•	Files will sync automatically every 24 hours.
•	Manual refresh can also be triggered via Q Business Data Sources → Sync Now.

3. Managing Access

•	To grant new coaches access:
o	Add them to the CareerCoaches group in IAM Identity Centre.
o	Apply existing ACL to maintain consistent access restrictions.

4. Moderation Controls

•	Global blocked keyword list is managed in Q Business Admin Console → Global Controls.
•	Admins can add or remove terms based on company policy.
________________________________________
🧾 Testing and Validation

✅ Functional testing with sample CVs and job descriptions confirmed:

•	Accurate skill-gap mapping
•	Relevant and diverse training suggestions
•	Correct enforcement of ACL restrictions
•	Successful daily sync from S3
📊 Efficiency Improvement: Manual analysis reduced from hours to seconds.
________________________________________
🧠 Key Features

•	🔍 Automated skill-gap detection
•	🎓 Personalised training recommendations
•	🧩 Dynamic integration with S3 training catalogs
•	🧑🏫 Real-time coaching refinement
•	🛡️ Role-based access and content moderation
•	🔁 Automated daily data synchronisation
________________________________________
🧱 Project Deliverables

Deliverable	Description

Amazon Q App: Fully functional AI coaching assistant
S3 Bucket & Catalogs	Dynamic course data integration
ACL File	Access Control Enforcement
Screenshots	UI, data sources, ACL verification
Output Report (PDF/Word)	Sample Skill Gap & Training Recommendations
________________________________________
📚 Learning Outcomes

Through this implementation, I mastered:

•	Building AI-powered business apps using Amazon Q Business.
•	Designing scalable no-code solutions integrated with AWS services.
•	Implementing secure role-based access control via IAM & ACL.
•	Applying content moderation policies at the enterprise level.
•	Delivering production-ready documentation and deployment strategies.
________________________________________
🏁 Conclusion

The Career4All Coaching App transforms a traditionally manual, inconsistent coaching workflow into a fully automated, intelligent, and scalable platform — empowering career coaches with real-time, data-driven insights.
This solution represents a practical example of how AI and AWS cloud automation can revolutionise professional coaching, training management, and workforce development in modern enterprises.
________________________________________
🧾 Repository Structure

career4all-coaching-app/
│
├── /screenshots Folder/
│   ├── interface.png
│   ├── datasources.png
│   ├── acl_access.png
│   ├── blocked_keywords.png
│
├── /outputs/
├──skill_gap_analysis_report.docx
├──output_generation_report.docx
├── career4all_acl.json
├── README.md
└── project_report.docx
________________________________________
