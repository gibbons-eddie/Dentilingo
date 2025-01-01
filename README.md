Dentalingo

![final presentation2](https://github.com/user-attachments/assets/b3647be2-87e8-43b0-8985-9a9c03a7160e)

# A Language Learning Application for Dental Students in Thailand

### Eddie Gibbons  
Matina Mahasantipiya  
Yuchen Xiong  
Brian Koehler  
Jayden Jones  

**CIS4914 Senior Project**  
**Spring 2022**  
**Department of CISE**  
**University of Florida**  

---

## Advisor:
**Dr. Tanida Srisiwan**  
University of Chiang Mai Faculty of Dentistry  
tanida.srisuwan@cmu.ac.th  

---

## Abstract

Language learning applications have proven to be a great resource for people to learn a language easily and conveniently. Rosetta Stone and Duolingo are some of the more popular services. However, these services give a general framework to cover all the major aspects of the languages that you can learn. There aren’t too many apps that focus on learning a language for a specific role or job. These apps also struggle with including auditory exercises to allow more hands-on learning for these people. On top of this, people in other parts of the world trying to learn English struggle to understand native English speakers compared to people from their same country speaking English. These apps only have one accent, one person speaking the language being learned, so learners again aren’t getting a complete scope of the language since it’s restricted from the perspective of only native speakers. More language learning apps need to be more tailored for specific roles and people to increase their effectiveness. By providing more context and information to different aspects of English for example, people can find better and more complete resources for their work, school, and recreational environments.

Our application aims to do just that; by focusing on dental terminology for Thai dental students, we have built an interface with varying difficulties that cover multiple clinic scenarios and modules for each aspect of dentistry. We built each module with common phrases and terms used daily in these clinics and created exercises based on 3 varying difficulties. Using the Flutter framework paired with a database run by SQLite, we have built a product for students and tailored the in-app experience to allow for the most comprehensive summary of English dental terms.

---

## 1. Introduction

Our software application presents a cohesive learning platform for Thai students to learn the English language within a clinical environment. This report provides a summary of my group’s full development process, from inception to a built application for teaching English grammar and pronunciation to Thai dental students. Our goal was to provide a complete application that could be used as the groundwork for more situations and more applications in the dental field.

The software that we developed using the Flutter kit is compatible with many other platforms, including web and mobile devices.

---

### 1.1 Problem Domain

Computer-based learning technology has only grown in recent years. Students in all grades have grown accustomed to online learning interfaces, such as Canvas, and have performed in online and virtual lectures through video conferencing software such as Zoom, especially in recent years. However, there hasn’t been a virtual language learning application equivalent to the in-person class experience. There have existed apps that teach various dialects such as Udemy and Mango Languages for many years, but they just don’t apply to everyone in the way that Canvas and Zoom have dominated their respective computer-based learning fields. Our application is a first step towards directly applicable education technology that has a singular focus on one area, one field of a language. Our solution to this is our application that we have created for Thai dental students, which we built for students and teachers at the university to be able to use to better learn English so they can communicate with their English-speaking clients more effectively. We have a progression system in place that will take students through the focal parts of English grammar and reading comprehension that utilizes many familiar exercises and also innovative learning practices.

---

### 1.2 Literature Overview

In order to build this application to provide as complete of a language learning experience as possible, we had to first research where other similar platforms got their success. Being the most popular for quite some time now, Duolingo has dominated when it comes to mobile education applications. Students familiar with the platform cite this as the biggest benefit of using the service: the mobility [1]. Despite this, it has never escaped being the complement to learning foreign languages, and it has remained secondary to an official curriculum to this day. It does help students in their language courses, but Duolingo could take a stronger foothold in that area of computer-based learning if the content provided was as expansive as the curriculum found in schools.

To cover all these bases, a language learning application couldn’t leave much to error. Its exercises need to be varied, and many options would need to be put in place to allow for multiple ways of learning [2]. There should be some progression system in place as well as a scoring system so students can view their progress statistically. One study, however, reveals another important aspect to effectiveness of language learning platforms: speaking accents. People in Thailand revealed that they are conscious of their accents and want to be able to be understood in their own accents [3]. Students at the Chiang Mai Faculty of Dentistry reflect this, and they put in their feedback that they struggle to be understood because of their accent, despite speaking grammatically correct English.

This is found not only between Thai-English speakers, but also Japanese-English speakers as well as Burmese-accented English speakers. The strong opinions are this matter are proof that the way in which auditory exercises are completed is important in how users understand and view auditory exercises on this, since the findings were that Thai-English speakers understood English the best when it was their one of their own speaking [4]. And since many apps like Duolingo use English speaking functions for their exercises, it’s no wonder why these apps haven’t broken much ground into a grander use for nonnative English speakers attempting to learn English. In the Mahidol University study, it was discovered that American speakers were rated the least intelligible for Thai EFL learners [5].

---

## 2. Technical Approach

### 2.1 Solution (Technical Approach)

To help nonnative English speakers get better-focused assistance with learning the English language as well as improve their confidence with their accents, our team has developed **Project Dentalingo**, an English language learning mobile application made and catered for Thailand students in dentistry. Using the Flutter development kit, we are able to support our platform on any device that these students use on a day-to-day basis. 

Project Dentalingo has been built from what users expect from other popular language education apps, but with a centered approach to teaching English terms and phrases through various exercises and accents to gain a broad sense of how the language is used. This interface allows for personal statistics, quizzes and flashcards, and operation categories to provide dialect help on any part of any dental procedure. We have used a local SQL database to store data on each user, and for each module and type of exercise, populating them from real-world examples to give our users as good of a learning resource as possible. The hierarchy of our data tables in our local database goes as such:

---

### 2.2 Results (Technical Approach)

For all these components of our application, we made sure to consult with both professors and students at the Chiang Mai Faculty of Dentistry to form our types of exercises and phrases. This also applies to the overall look of our app; we wanted to keep the UI minimal but efficient with a clear colorway for visual appeal. We wanted any users of Project Dentalingo to be able to practice and hone their English skills without much setup time. 

In our wireframe for our planned Modules page, we display various images to represent all our different modules and what content encompasses each of them. Each module, phrase, and term stems from multiple tables in our local SQL database. For our various testing phases, I initially set up individual tables for phrases, terms, and modules using the SQFlite Flutter package. It wasn’t until after I created the prototype modules page that I realized that they didn’t need to load in the database like the terms and phrases were. I performed several SQL queries into the database that load sample phrases and terms that had the module name that they were categorized under based on the module that is selected in the application. Essentially, a separate query is executed that filters the results based on the module name, each time a module page is loaded.

This was the main way Yuchen and I figured out how to parse through all the recordings and load the correct ones based on the correct advanced operation submodule. We built a whole Flutter class and component for these individual “phrase cards,” as we dubbed them, where we designed the layout of the phrases and all the interface buttons on it. The class has two built-in functions that query the information necessary from the database and also load the correct recording from the local audio assets.

---

### 2.3 Technical Challenges and Solutions

The largest challenge myself and many others were faced with was integrating SQLite functions into our Flutter-based application. There was a Flutter package called “SQFlite” that we decided to use, but connecting it to the database I initially created was tougher than I could’ve imagined. Basically, since we were running our app in an emulator during most of our production, the simulator would run our app with its own internal database that it was linking itself to every time. We had to manually create a function that would run on startup that would copy the database file’s contents over to the local one of the simulator so that all our data tables could be queried and referenced as intended.

Another challenge I struggled with was structuring the layout of the pages. I wanted every module component and file to be organized neatly into the repository, but since I had little to no knowledge of Flutter app development, I had to research organizational conventions and also what each project file was responsible for. Each time we added a new dependency, we had to manually edit the `pubspec.yaml` file and reload our build of the app in order for it to function properly.

---

## 3. Conclusions

I was tasked with both frontend and backend tasks for our language learning application. As I had never used Flutter before, I had to learn how to build menus, widgets, and buttons for the app’s user interface as well as create the advanced exercises widgets for the audio playback of the phrases and text controllers to record user inputs. I worked on the structure of the overall project files and built the initial database with all of the important data points necessary for phrases and terms used in our exercises.

I believe the overall project structure is organized and clean, but I definitely feel that the implementation of the advanced exercises I worked on could be done better. I want to make the functions more variable, even though we did hardcode some of them in the beginning for ease of testing. And in my design for the phrase cards, I feel like they could appeal to the eye better. As I stated before, my experience with Flutter continues to grow with the development of this project, and so, I am currently focused on the functionality before I clean up the designs.

Throughout this project, I have learned to work in a team environment. My teammates have been helpful and communicative with their feedback, which I find very important. I wanted everyone to be giving their thoughts on how to move forward with the app design and features, even if we weren’t working on the same things. We all want this project to be a success, and that means that teamwork should be encouraged across all facets of the team. If the plan for us to continue working on this application with Dr. Tanida stays true, we want to improve the project with more animations, more exercises, and more personal user statistic data.

---

### 3.1 Standards and Constraints

**Standards:** All programming conformed to the Dart Programming Language Specification 5th edition, which is an ECMA standard. Both a Dart VM with just-in-time (JIT) compilation and an ahead-of-time (AOT) compiler were employed.  

**Constraints:** All software was developed to run in real time and was required to run on a mobile device or a mobile simulator.

---

### 3.2 Acknowledgements

The author would like to thank his advisor, Dr. Tanida. Her aid with conducting the meetings between us and the student was really appreciated to garner feedback and ideas for the application.

---

### 3.3 References

1. Munday, Pilar. (2015). _The case for using Duolingo as part of the language classroom experience._ RIED. Revista Iberoamericana de Educación a Distancia. 19. 10.5944/ried.19.1.14581. 
2. Nushi, Musa, and Mohamad Hosein Eqbali. “DUOLINGO: A MOBILE APPLICATION TO ASSIST SECOND LANGUAGE LEARNING.” The Journal of Teaching English with Technology, vol. 17, no. 1, pp. 89–98. [Read Full Text](https://files.eric.ed.gov/fulltext/EJ1135889.pdf)
3. Ambele, Eric A., and Yusop Boonsuk. “Thai Tertiary Learners’ Attitudes towards Their Thai English Accent.” PASAA, vol. 61, Jan. 2021, pp. 87–110. 
4. Kalra, Rusma, and Chayada Thanavisuth. “Do You like My English? Thai Students’ Attitudes towards Five Different Asian Accents.” _Arab World English Journal_, vol. 9, no. 4, 2018, pp. 281–294. [DOI](https://doi.org/10.24093/awej/vol9no4.21)
5. Doloh, Sunaisah, and Natthapong Chanyoo. “Relationships between Thai EFL Learners’ Factors, Intelligibility, and Comprehensibility towards Varieties of English.” _Theory and Practice in Language Studies_, vol. 12, no. 1, 2022, pp. 46–54. [DOI](https://doi.org/10.17507/tpls.1201.06)

---

### 3.4 Diagrams and Charts

![final presentation5](https://github.com/user-attachments/assets/4b6efc69-87e4-4e46-9927-fb5b66d01993)

![final presentation6](https://github.com/user-attachments/assets/17c301be-58b6-4f14-85b5-2d6d13c662c6)

![final presentation7](https://github.com/user-attachments/assets/54d484d2-4b34-4df7-b9b1-7cf6be925d4a)

![final presentation8](https://github.com/user-attachments/assets/f201d486-2214-4dd3-9681-db58fdee11c5)
