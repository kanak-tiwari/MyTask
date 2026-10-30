# MyTask - Task Management App

Stack: Hibernate 6.4 + Jakarta Servlets/JSP + MySQL 8 + Maven (WAR) + Bootstrap 4.
Tomcat **10.1+** chahiye (Tomcat 9 par nahi chalega).

## Run karne ke steps
1. MySQL start kijiye (XAMPP/MySQL Workbench). User `root`, password khaali (hibernate.cfg.xml me badal sakte ho).
2. Database `sampledb` khud ban jaata hai. **Purani `task` table ek baar delete kijiye** (ID ab auto-increment hai):
   `DROP TABLE IF EXISTS sampledb.task;`
3. Eclipse me purana `ProjectOne` project workspace se hata dijiye (Delete, contents mat delete karna), phir
   File > Import > Maven > Existing Maven Projects se `MyTask` folder import kijiye.
4. Project par right-click > Maven > Update Project (Alt+F5), Force Update tick karke OK.
5. Project par right-click > Run As > Run on Server > Tomcat v10.1.
6. Browser: http://localhost:8080/MyTask/

## Features
Task add, show, update, delete (CRUD) with Hibernate + MySQL.

## Fixes (original version se)
- Task ID random ki jagah database AUTO_INCREMENT
- web.xml ki bekaar line hata di
- Delete GET link ki jagah POST form + confirm box
- Output escape hota hai (XSS se bachav), Unicode/Hindi text sahi save hota hai
- Database ka code JSP se nikalkar `DbOps` class me, sessions try-with-resources se band hote hain
- Task na mile to crash nahi hota, title empty nahi ho sakta, content limit 2000 characters

## Abhi bhi baaki
- Navbar ka Search box kaam nahi karta (sirf design hai)
- Login/users nahi hain, koi bhi task edit/delete kar sakta hai
