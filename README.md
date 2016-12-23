                                                       ECAMS DOCUMENT FOR REFERENCE
                                                               ================

There are three types of pages
  1-List Page
  2-Detail Page or General page
  3-Dialog page

Common set up for project
==========================
1-Change local.properties file
2-Change jboss.application.properties file

Refer to PE Build instruction document

Run the project
------------------
1-run the provider-build.xml file
2-run the jboss server
3-After completion, give the URL in browser and run the project.

Task
-----
1--create a link in provider page which point to genericList page.
2- create a link in provider page which point to custom static page(Detail page)
3-create a tab and show the dialog page.

Flow of search the page
-----------------------
->below of the page there is a page action name(like Page ID: pgProviderGeneral(Provider)  ), based on this name we have to search that name in  the corresponding action.xml file to know the jsp page and Handler.
 
Search result:
1-prvdr_action.xml
2-ProviderListPage.xml

Common Control Flow:
------------------------------    
1-ListPage.xml ---We know the List page details, js, and additional jsp.
2-Action.xml---We know the jsp and Handler details.
.jsp--→*._action.xml----->providerListPage.xml--->handler


->CNSI jar present in side UTMMIS_Lib which is in side workspace.

one use case
------------
If you want to see both list page and detail page follow the below step----

step
------  
1-goto Prvdr_action.xml and set like below
<Page name="pgChitta" URL="/common/pgGenericList.jsp"
			

2--goto ProviderListPage.jsp  and the JSPInclude like below
<Page name="pgChitta"
            Javascript="include/javascript/provider/chitta.js"
            HiddenField=""
            Title="Employee List"
            ShowMenu="N"
            IDField="IDField"
			JSPInclude="/provider/enrollment/chittalistpage.jsp">

chittalistpage.jsp-----physical jsp page
pgGenericList.jsp---→Generic list page


----------------------------------------------------------------------------

->All the SQL related method are kept inside DbUtilImpl.java class which is in CNSI package.
-> All the SQL related Method Kept inside DbUtilImpl.java Class.
->To see all method inside the class(Ctrl+o).

how to increase jvm size in jboss
---------------------------------
steps
----
1-


2

3--



                                                                                                                                                                                            
time setup in jboss
==============     


                                           

Important project link

as-one :    http://cnsicti21.cns-inc.com:8080/AsOneWeb/pages/pgLogin.faces 
Credential same as system credentials

url for eCAMS: http://10.11.11.35:9080/ecams/jsp/common/pgLogin.jsp
 
Credential: DHMH / supuser / dshs123$
http://10.86.24.6:8080/Time_Sheet/  -----TimeSheet
http://cti.cns-inc.com/ctiess -----ESS PORTAL

CNSI course learening
-------------------------------  

url:  https://www.learnsmartsystems.com/login/default.aspx?bid=176&login_rd=http%3a%2f%2fcloud.learnsmartsystems.com%2fdefault.aspx 

credential: chittaranjan.kar@cns-inc.com
                   LearnCourse

ECAMS DEMO URL
==================
url:  http://10.11.11.35:9080/ecams/jsp/common/pgLogin.jsp
 
Credential: DHMH / supuser / dshs123$
CTI URL:
----------
http://10.86.24.51:19090/ecams/jsp/common/pgLogin.jsp  - CTI Linux server environment. 
supuser / dshs123$ / UTAH 

112  url
---------   
http://10.14.11.112:38080/ecams/jsp/common/pgLogin.jsp - 112 RDC machine environment. 
Credential as above

RuleIT composer:

UN:supuser
PWD:dshs123$


NOTE:
1→For hiding the column value we have to use “HideColNames” attribute of “page” tag.

25/03/15
-----------

1.       Is Managed care covers only Medicaid (since described for states)? Not Medicare?
[Ankit]: Usually in case of most of the states, we exempt the managed care Recipient from Managed Care if the Recipient is enrolled in Medicare. Which means till the time Managed Care Recipient is receiving Medicare Coverage, the member can no longer get Managed Care coverage. In case of Utah Managed Care Recipient can still be enrolled in both Medicare and Managed Care and member will get coverage from both of these programs.
 
2.       Is a mandatory thing for a member, to enrol in MCO ?
[Ankit]: If the Managed Care eligible member lives in Voluntary county, then it is up to the member to decide if the member wants to enroll in Managed Care Program or not. In Mandatory counties members need to enroll in Managed Care Program.
 
3.       What happens, if a medical cost exceeds a capitation collected from enrolee?
[Ankit]: Since the MCO gets the fixed monthly capitation payment from state for covering the Managed Care Member, it is MCO’s responsibility to cover all expenses for providing care to the member. MCO submits encounters for all of the member Provider visits which are used at the end of the year to determine if the capitation payment rate for the next year’s capitation payment needs to be increased by the state. This calculation is performed by state actuary’s.
 
4.       Is capitation amount is based on the service provided for the member, or it’s based on the program?
[Ankit]: Capitation rates are based on Specific Rate Code. Usually it is a 2-3 digit code which is determined based on members age, gender, demographic factors etc.
 
5.       Who will define/ approve the programs?
[Ankit]: State defines/approves the programs. During go live we will create the Program configuration via backend which will be approved by state worker. Later on if state wants, they can add/modify program configuration via managed care screen and submit it for state approval workers approval.
 
6.       What are all the subsystems involved with Managed Care?
[Ankit]: Provider, Claims, Reference, EDI, TPL, Care Management, Finance, Member
 
7.       What is role of rules engine(RuleIT) with managed care?
[Ankit]: It is used for managed care enrollment and payment edit maintenance and processing.
 
8.       What is Co-Pay Means?
[Ankit]: When a member visits providers for outpatient visit, they are usually required to make a onetime small payment(i.e. $5) from their pocket which is called as Out of Pocket.
 
9.       What is service based enhancement payment?
[Ankit]: In case of Utah deliver is considered as an example of service eligible of Enhancement Payment. Apart from regular capitation payment, MCO’s do get fixed enhancement payment for every delivery case of its pregnant members who deliver baby.

Mono ans
------------    
1.       Is Managed care covers only Medicaid (since described for states)? Not Medicare? [Mano] Managed care cover Medicaid, CHIP and Medicare members
2.       Is a mandatory thing for a member, to enrol in MCO ? [Mano] It’s based on their county where they live
3.       What happens, if a medical cost exceeds a capitation collected from enrolee? [Mano] Capitation in not collected from Medicaid members
4.       Is capitation amount is based on the service provided for the member, or it’s based on the program? [Mano] Based on Program and Contract
5.       Who will define/ approve the programs? [Mano] State
6.       What are all the subsystems involved with Managed Care? [Mano] Depends upon each state, in UTAH it is Member, TPL, Care Management, Claims, Finance, EDI, Reference
7.       What is role of rules engine(RuleIT) with managed care? [Mano] Member enrolment maintenance
8.       What is Co-Pay Means? [Mano] Google…
9.       What is service based enhancement payment? [Mano] Some service may be very costly for MCO, so state pays special (enhanced) payments for those service.

31-03-15
---------- 
Question: when I tried to add a new RAC/Category of aid its showing a set of available RAC/Category of aid , but if I want to a add a new RAC/Category of aid how can It be done, regarding this please clarify.
[Ankit]: RAC codes are added in Member Subsystem and not in Managed Care. In Managed Care, we can only associate these RACs to the Managed Care Program.
 
Question: why the Default enrollment, reenrollment, New Born/Family Reconnect limits will be always set as “Open”. what happens if we set as “Close”?
[Ankit]: These limits are set to ‘Open’ to allow the enrollment, reenrollment, New Born/Family Reconnect. If any of these limits are closed, we can not enroll, reenroll, New Born/Family Reconnect enrollment to the selected MCO.
Question: What is meant by Broker outreach days, MCO outreach days, Monthly Payment Cut-off Days ?
[Ankit]: “Broker Out Reach Days” is not applicable for Utah. It is applicable in states where Enrollment Broker is used by states to reach out to the Member to get their MCO selection preference. “MCO Out Reach Days” refers to number of days MCO gets to print and send Member ID Cards. “Monthly Payment Cut-off Days” refer to how many days before the Month End next month capitation payment will be generated by PRISM.
Question: Can a member have one or more rate codes?
[Ankit]: No, Member can have only one Rate Code assigned to them based on demographic and other factors.
Question: Who can override the member data?
[Ankit]: State person with appropriate access can override the Rate Code. Please refer the Actor section in respective use case.
Question: Is it possible to get enroll a member in multiple service areas and get treatment from multiple providers ?
[Ankit]: No, Member Enrolls in a residential service area based on their zip code. The Service Area selection happens based on this zip code. Only one PCP is assigned to the member though based on the need member can get prior authorization to visit specialist providers.
demographic factors

Socioeconomic characteristics of a population expressed statistically, such as age, sex, education level, income level, marital status, occupation, religion, birth rate, death rate, average size of a family, average age at marriage. A census is a collection of the demographic factors associated with every member of a population.
1) What is a prior authorization?
A prior authorization is an extra step that some insurance companies require before they decide if they want to pay for your medicine. 
2) What medicines require a prior authorization?
I. Brand name medicines that have a generic available. A generic medicine is a medicine that contains the same active ingredient as the brand name drug but is available at a lower cost. 
II. Expensive medicines.
III. Medicines with age limits. Retin-A®, a topical acne treatment, is an example. Acne is considered to be a condition of children and young adults. Retin-A® may not be covered if the person is over a certain age. This age can vary and is usually determined by the insurance company.
IV. Drugs used for cosmetic reasons. For example, Propecia®, which is prescribed to re-grow hair or to prevent hair loss. 
V. Drugs prescribed to treat a non-life threatening medical condition. These drugs are usually not needed to maintain life. An example is erectile dysfunction drugs such as Cialis®. 
VI. Drugs not usually covered by the insurance company, but said to be medically necessary by the doctor. Many different drugs can be used to treat the same condition. If a patient requires a particular medicine, the doctor must inform the insurance company that there are not any other medicines that would work in the patient. 
VII. Drugs that are usually covered by the insurance company but are being used at a dose higher than “normal”. 
3) What should I expect if my medicine needs a prior authorization? If your insurance company requires a prior authorization on one of your medicines, it usually means the insurance company needs more information before they can decide if they want to pay it. 
Becoming familiar with the prior authorization process may enable you to get your medicine approved faster. But beware, not all medicines will be approved. Even if you do everything right, the insurance company may still refuse to cover your medicine. In the end, the insurance company is the one making the decision. 
4) What should I do if my medicine needs a prior authorization? If the pharmacist tells you that your medicine requires a prior authorization then you should:
√ Contact the doctor who prescribed the medicine and let them know that your medicine requires a prior authorization.
√ Ask your doctor how long it usually takes for them to contact the insurance company and fill out the appropriate forms.
√ Contact your insurance company and make sure there are not any additional steps you need to take. Sometimes an insurance company may want you to fill out some paperwork or sign some forms.
√ Allow the doctor’s office and insurance company enough time to complete their end of the process.
√ Check back with the pharmacy to see if the prior authorization was approved.
√ If your medicine is not approved, call your insurance company and find out why.
5) What are some of the reasons why a prior authorization may not be approved?
	You did not give your insurance company, doctor, and pharmacist enough time to complete the needed steps. 
	Your insurance denied your prior authorization claim. 
	Your doctor’s office forgot to contact your insurance company. 
	Your pharmacy may not be billing your insurance company properly. Sometimes when billing for a medicine that needs a prior authorization, a special billing code is needed. The pharmacy could have received the wrong prior authorization code. 
What kinds of drugs need prior authorization?
•	Drugs that have dangerous side effects 
•	Drugs that are harmful when combined with other drugs 
•	Drugs that you should use only for certain health conditions 
•	Drugs that are often misused or abused 
•	Drugs that a doctor prescribes when less expensive drugs might work better 
EDI 834 Benefit Enrollment and Maintenance:
The EDI 834 transaction set represents a Benefit Enrollment and Maintenance document. It is used by employers, as well as unions, government agencies or insurance agencies, to enroll members in a healthcare benefit plan. The 834 has been specified by HIPAA 5010 standards for the electronic exchange of member enrollment information, including benefits, plan subscription and employee demographic information.

The 834 transaction may be used for any of the following functions relative to health plans: 
•	New enrollments 
•	Changes in a member’s enrollment 
•	Reinstatement of a member’s enrollment 
•	Disenrollment of members (i.e., termination of plan membership) 
The information is submitted, typically by the employer, to healthcare payer organizations who are responsible for payment of health claims and administering insurance and/or benefits. This may include insurance companies, healthcare professional organizations such as HMOs or PPOs, government agencies such as Medicare and Medicaid.

A typical 834 document may include the following information: 
•	Subscriber name and identification 
•	Plan network identification 
•	Subscriber eligibility and/or benefit information 
•	Product/service identification 
EDI 820 Payment Order/Remittance Advice:
The X12 820 transaction set provides the EDI format for transmitting information relating to payments. It is typically used in conjunction with an electronic transfer of funds for payment of goods, insurance premiums or other transactions. The actual funds transfer is often coordinated through the Automated Clearinghouse (ACH) system, and an 820 may be effectively wrapped in an ACH banking transaction.

The 820 transaction is used in a number of situations: 
•	by businesses to provide instructions to banks for making a payment, such as a funds transfer, to a payee 
•	by businesses directly to individual suppliers to communicate the details of a pending payment, including adjustments reflected in the payment 
•	by companies providing premium payment information to health insurance plans 
Medicare is a social insurance program administered by the United States government, providing health insurance coverage to people who are either age 65 and over, or who meet other special criteria. It was originally signed into law on July 30, 1965 by President Lyndon B. Johnson as amendments to Social Security legislation.

Medicaid is the United States health program for individuals and families with low incomes and resources. It is an entitlement program that is jointly funded by the states and federal government, and is managed by the states.
07/04/15
----------------- 
COMMENT IN CODE:
We have to follow the below process in our coding side.
 
Sample :                                         //IT:002 FIN-001 R5-FIN-UC069 CTI

Single line comments:                //IT: <Iteration> <Story No> < Use Case No>CTI 
Multiple line:                               //IT: <Iteration> <Story No> < Use Case No>CTI Start 
                                                      //IT: <Iteration> <Story No> < Use Case No>CTI End
Business rules:              //IT: <Iteration> <Story No> < Use Case No>CTI BR:<business rule No>
Method declaration:
/**
* <Story Title> 
* @author <name>
* <Iteration> <Story No> < Use Case No>
* summary of the method
*/
New jsp creation : 
/**
* Filename: <files name with extension>
* <p>
* JSP for <description>
* @author : <name>
* <Iteration> <Story No> < Use Case No><date>
*
*/

New Java creation:
/**
* Filename: <files name with extension>
* <p>
* <description about the class>
* @author <name>,Copyright (c) CNSI 2006-2008, 
*All Rights Reserved.
* @since <date>
* @version 1.0
* @see <files name>
* <Iteration> <Story No> < Use Case No>
*/
Modify Java creation:
/**
* Filename: <files name with extension>
* <p>
* <Iteration> <Story No> < Use Case No>
* <description about the class>
* @author <name>,Copyright (c) CNSI 2006-2008, 
*All Rights Reserved.
* @since <date>
* @version 1.0
* * ==================================================================
* Modification History
* ====================================================================
* SL No Change No Author Description
* =====================================================================
*/
 
NEW DB DETAIL:
Tnsnames details.
 
utdev =
  (DESCRIPTION =
    (ADDRESS_LIST =
      (ADDRESS = (PROTOCOL = TCP)(HOST = 10.86.24.52)(PORT = 1521))
    )
    (CONNECT_DATA =
      (SERVICE_NAME = utdev)
    )
  )
 
Schema Name/Password Details
 
Schema Name	Password	Owner
Prismdevr5	prismdevr	Gaja
prismdev_remc	prismdev_remc	 
prismdev_recl	prismdev_recl	 
prismdev_repa	prismdev_repa	 
 	 	

Change oracle_ds.xml file


SOLID (object-oriented design)
------------------------------------------------   
In computer programming, SOLID (Single responsibility, Open-closed, Liskov substitution, Interface segregation and Dependency inversion) is a princple required to remove code smells by causing the programmer to refactor the software's source code .

Initial	Stands for
(acronym)	Concept
S	SRP [4]
Single responsibility principle 
a class should have only a single responsibility (i.e. only one potential change in the software's specification should be able to affect the specification of the class) 
O	OCP [5]
Open/closed principle 
“software entities … should be open for extension, but closed for modification.” 
L	LSP [6]
Liskov substitution principle 
“objects in a program should be replaceable with instances of their subtypes without altering the correctness of that program.
I	ISP [7]
Interface segregation principle 
“many client-specific interfaces are better than one general-purpose interface.”[8] 

D	DIP [9]
Dependency inversion principle 
one should “Depend upon Abstractions. Do not depend upon concretions.”[8] 


→ use C:\Users\karc\MC_WORKSPACE\JavaSource\ECAMS-JAR\src\com\cnsi\managedcare instead of datadictionary.java
some RAC information
-----------------------------------   
1→One person have one county.
2→one person have one RAC code
3→For example one person in one time period(1/1/15---31/1/15). Here he has one county and one RAC code. Then he change its time period(1/3/15---31/1/15).Then he has same county but he may add different RAC(only one).

In jboss server ejb instance already exist error solution
------------------------------------------------------------------   
/UTAH_MC/JavaSource/ECAMS-JAR/src/com/ecams/processor/ejb/META-INF/jboss.xml
change:
 <!--  Report Content Management changes start 
         <session>
            <ejb-name>ContentManagementReportsLoaderEJB</ejb-name>
            <jndi-name>ejb/processing/ContentManagementReportsLoaderProcessor</jndi-name>
        </session>
         Report Content Management changes end -->
 in line 14 change I.e remove comment

to update the sub menu
------------------------------- 
UPDATE application_menu
SET APLCTN_MENU_NAME  ='MC Specific Rate Code List',
  modified_date       =sysdate
WHERE APLCTN_MENU_NAME='MC Rate List';


PLSQL datewithtimestamp 24 hour format
-------------------------------------------------   
TO_CHAR(MEB.MODIFIED_DATE,'MM/DD/YYYY hh24:mi:ss')


url : http://10.86.24.1:8180/jenkins/

Username/password : utahmc/utahmc

For Sonar analysis report (use for code review so that you can make quality code)

url : http://10.86.24.1:9001/
username/password : UTAH-MC/UTAH-MC

Tracebility matrix SVN link. We have to use it from IT-07 unwards
-------------------------------------------------------------------------------------  
Simply checkout the tracebility  matrix and change the text and check in in svn

                https://c5appvm.cns-inc.com/svn/Utah_MC/Project Management/Engineering/Tracelibility_Matrix


-We should  maintain unittest document and raise the unittest bug and review bug in as one.



List page
-------------  
	To disable the list page button we also use DisableControl attribute in ManagedCareListPage.xml
E.g <Button name="RejectButton" value="Reject" DisableControl="Y"
				onclick="javascript:submitMCPage('frmGenericListPage','Reject');				CSSClass="ibtn i-icon i-icon-ban-circle" />
select table based on column name
------------------------------------    
SELECT TABLE_NAME ,
  COLUMN_NAME
FROM ALL_TAB_COLUMNS
WHERE COLUMN_NAME LIKE 'BATCH%'
AND TABLE_NAME LIKE 'MC_%' ;

Documentation comment of class method:
e.g-             
1->
/**
 * This is the public method for getting the lookup code and value paires for
 * specific table and column. Return is the map of lookup code and values. The key
 * for the map is lookup code.
 * 
 * @param p_sTableName Parameter variable of type String table name
 * @param p_sColName Parameter variable of type String col name
 * @param p_sDomainName Parameter variable of type String domain name
 * 
 * @return the look up code and values
 * 
 * @throws CNSIException the CNSI exception
 */
  public Map getLookUpCodeAndValues(String p_sTableName, String p_sColName, String p_sDomainName) throws CNSIException
2->
/**
 * Filename: LookUpCacheManager.java
 * <p>
 * This is the class for caching the static look up values. The database
 * tables it access are: lookup_value, lookup_target.
 * The class is not modified or update any value into the database tables.
 * 
 * To get the instance of LookUpCacheManager, refer to the detail of Cache Framework.
 * 
 * @author: Jing He, Copyright (c) CNSI 2001-
 * 2002, All Rights Reserved.
 * @since: October 25, 2001
 * @version: 1.0
 */

public class LookUpCacheManager implements CacheManager
RuleIT Information:
-------------------------------   
Step-1: We need to paste 2 dll file in window in C drive.
dffsetup-msvcr71.dll
msvcr71.dll
step-2: We need to install RuleITComposerInstaller file.(Automatic)
Step-3: We need to paste ojdbc6.jar file in install ruleit folder lib.

Some Common js Function:
1.	validateDynamics()------Field check
here we can check the field based on some common letter like-n,r,fld,fhdn,cmb,chk etc.

Agile Methodologies
Contributed By: Ravi Sundararaman, Cloud Migration, CNSI CTI.
Agile Methodology is becoming popular and catching up with the IT industry because of the following reasons: 
	It helps teams embrace rapid changes & increase adaptability with customers easily.
	It helps teams to mitigate risks at early stages of product life-cycle.
	Customers see the visible progress as they are able feel of working software.
	Customers give feedback at every stage of the product life cycle, since they are part of the product development.
	Early adaptation of feedback leads to a system that meets the needs of various stakeholders.
	Complexity of the features are properly prioritized and easily managed by the team.
	Team has chance to learn from mistakes during each iteration of development.
The various agile methodologies share much of the same philosophy, as well as many of the same characteristics and practices. But from an implementation standpoint, each has its own recipe of practices, terminology, and tactics. Here we have summarized a few of the main agile software development methodology contenders:

 

Scrum Methodology
Scrum is a lightweight agile project management framework with broad applicability for managing and controlling iterative and incremental projects of all types. Ken Schwaber, Mike Beedle, Jeff Sutherland and others have contributed significantly to the evolution of Scrum over the last decade. Scrum has garnered increasing popularity in the agile software development community due to its simplicity, proven productivity, and ability to act as a wrapper for various engineering practices promoted by other agile methodologies.
With Scrum methodology, the “Product Owner” works closely with the team to identify and prioritize system functionality in form of a “Product Backlog”. The Product Backlog consists of features, bug fixes, non-functional requirements, etc. – whatever needs to be done in order to successfully deliver a working software system. With priorities driven by the Product Owner, cross-functional teams estimate and sign-up to deliver “potentially shippable increments” of software during successive Sprints, typically lasting 30 days. Once a Sprint’s Product Backlog is committed, no additional functionality can be added to the Sprint except by the team. Once a Sprint has been delivered, the Product Backlog is analyzed and reprioritized, if necessary, and the next set of functionality is selected for the next Sprint.
 
Scrum methodology has been proven to scale to multiple teams across very large organizations with 800+ people. See how VersionOne supports Scrum Sprint Planning by making it easier to manage your Product Backlog.
Lean and Kanban Software Development
Lean Software Development is an iterative agile methodology. Lean Software Development owes much of its principles and practices to the Lean Enterprise movement, and the practices of companies like Toyota. Lean Software Development focuses the team on delivering Value to the customer, and on the efficiency of the “Value Stream,” the mechanisms that deliver that Value. 
Lean methodology eliminates waste through such practices as selecting only the truly valuable features for a system, prioritizing those selected, and delivering them in small batches. It emphasizes the speed and efficiency of development workflow, and relies on rapid and reliable feedback between programmers and customers. Lean uses the idea of work product being “pulled” via customer request. It focuses decision-making authority and ability on individuals and small teams, since research shows this to be faster and more efficient than hierarchical flow of control. Lean also concentrates on the efficiency of the use of team resources, trying to ensure that everyone is productive as much of the time as possible. It concentrates on concurrent work and the fewest possible intra-team workflow dependencies. Lean also strongly recommends that automated unit tests be written at the same time the code is written.
The Kanban Method is used by organizations to manage the creation of products with an emphasis on continual delivery while not overburdening the development team. Like Scrum, Kanban is a process designed to help teams work together more effectively.
Kanban is based on 3 basic principles:
•	Visualize what you do today (workflow): seeing all the items in context of each other can be very informative
•	Limit the amount of work in progress (WIP): this helps balance the flow-based approach so teams don ‘t start and commit to too much work at once
•	Enhance flow: when something is finished, the next highest thing from the backlog is pulled into play
Kanban promotes continuous collaboration and encourages active, ongoing learning and improving by defining the best possible team workflow.
Extreme Programming (XP)
XP, originally described by Kent Beck, has emerged as one of the most popular and controversial agile methodologies. XP is a disciplined approach to delivering high-quality software quickly and continuously. It promotes high customer involvement, rapid feedback loops, continuous testing, continuous planning, and close teamwork to deliver working software at very frequent intervals, typically every 1-3 weeks.
The original XP recipe is based on four simple values “ simplicity, communication, feedback, and courage “ and twelve supporting practices:
 
In XP, the “Customer” works very closely with the development team to define and prioritize granular units of functionality referred to as “User Stories”. The development team estimates, plans, and delivers the highest priority user stories in the form of working, tested software on an iteration-by-iteration basis. In order to maximize productivity, the practices provide a supportive, lightweight framework to guide a team and ensure high-quality software.
Crystal
The Crystal methodology is one of the most lightweight, adaptable approaches to software development. Crystal is actually comprised of a family of agile methodologies such as Crystal Clear, Crystal Yellow, Crystal Orange and others, whose unique characteristics are driven by several factors such as team size, system criticality, and project priorities. This Crystal family addresses the realization that each project may require a slightly tailored set of policies, practices, and processes in order to meet the project ‘s unique characteristics..
Dynamic Systems Development Method (DSDM)
DSDM, dating back to 1994, grew out of the need to provide an industry standard project delivery framework for what was referred to as Rapid Application Development (RAD) at the time. While RAD was extremely popular in the early 1990 ‘s, the RAD approach to software delivery evolved in a fairly unstructured manner. As a result, the DSDM Consortium was created and convened in 1994 with the goal of devising and promoting a common industry framework for rapid software delivery. Since 1994, the DSDM methodology has evolved and matured to provide a comprehensive foundation for planning, managing, executing, and scaling agile process and iterative software development projects.
DSDM is based on nine key principles that primarily revolve around business needs/value, active user involvement, empowered teams, frequent delivery, integrated testing, and stakeholder collaboration. DSDM specifically calls out “fitness for business purpose” as the primary criteria for delivery and acceptance of a system, focusing on the useful 80% of the system that can be deployed in 20% of the time.
Requirements are baselined at a high level early in the project. Rework is built into the process, and all development changes must be reversible. Requirements are planned and delivered in short, fixed-length time-boxes, also referred to as iterations.
Feature-Driven Development (FDD)
The FDD variant of agile methodology was originally developed and articulated by Jeff De Luca, with contributions by M.A. Rajashima, Lim Bak Wee, Paul Szego, Jon Kern and Stephen Palmer. The first incarnations of FDD occurred as a result of collaboration between De Luca and OOD thought leader Peter Coad. FDD is a model-driven, short-iteration process. It begins with establishing an overall model shape. Then it continues with a series of two-week “design by feature, build by feature” iterations. The features are small, “useful in the eyes of the client” results. FDD designs the rest of the development process around feature delivery using the following eight practices:
	Domain Object Modeling
	Developing by Feature
	Component/Class Ownership
	Feature Teams
	Inspections
	Configuration Management
	Regular Builds
	Visibility of progress and results
FDD recommends specific programmer practices such as “Regular Builds” and “Component/Class Ownership”. FDD’s proponents claim that it scales more straightforwardly than other approaches, and is better suited to larger teams. Unlike other agile methods, FDD describes specific, very short phases of work, which are to be accomplished separately per feature. These include Domain Walkthrough, Design, Design Inspection, Code, Code Inspection, and Promote to Build.
So Agile Framework helps teams to benefit like 
	Faster Time to Market.
	Reduce Uncertainty & Risk.
	Increase ROI by focusing on Customer Value.
And all the teams who want to carry out Agile can choose one of the above methodologies depending upon their team flexibility and adaptability. In my next blog article I will explain about Agile Values and Principles.
Notes:
p_mapRequestParameters contain multiple map.and map values are stored in table names.so 1st we need to get table name then we will get all the info of indivisual items.
Q->Why put comment(<!-- --> )in java script?
<script type="text/javascript">
   <!--
       // Code goes here
   -->
</script>

Ans: I know that the point is to prevent browsers that are incompatible with JavaScript from rendering the source, but is this still a best practice today? The vast majority of browsers used today can interpret JavaScript; even modern mobile devices usually don't have trouble.
How to create the Connection object in ECAMS?
Ans: Existing method:
    private Connection getConnection(UserDetails p_objUserDetails)
            throws CNSIException
    {
        try
        {
            return m_objDbUtil.getConnection(p_objUserDetails);
        }
        catch (Exception ex)
        {
            throw throwCNSIException(ex);
        }
    }
So call in below way:

 Connection l_objConnection = null; 
l_objConnection = getConnection(p_objUserDetails);

No need to call:

l_objConnection = m_objDbUtil.getConnection(p_objUserDetails);




Page Entry in Database: 
If a page must contain the UI screens in the Raptor framework, it must have an entry in the Page table. If this table is missing, you will not be able to create any UI screens. The user access level must be defined for each Page created inside the module. This access level can either be at page level or at control level. 
All pages that have an entry must allow full access to Super User. The page access can be provided through UI screens using Admin functionality or by applying DCRs. 
Sample script: 
INSERT INTO PAGE 
            (PG_SID, 
             PG_NAME, PG_LGCL_NAME, PG_DESC, 
             APLCTN_AREA_SID, 
             ENTRY_PAGE_FLAG, OPRTNL_FLAG, CREATED_BY, CREATED_DATE, 
             MODIFIED_BY, MODIFIED_DATE, 
             APLCTN_GROUP_LKPCD, 
             PG_SHORT_NAME 
            ) 
     VALUES ((SELECT NVL ((SELECT MAX (PG_SID) + 1 
                             FROM PAGE 
                            WHERE APLCTN_AREA_SID = X.APLCTN_AREA_SID), 
                          TO_CHAR (X.APLCTN_AREA_SID, '990000000') 
                         ) PG_SID_NO 
                FROM APPLICATION_AREA X 
               WHERE X.APLCTN_AREA_SID = 15), 
             'pgSamplePage', 'Sample Page', 'Sample Page Description', 
             (SELECT APLCTN_AREA_SID 
                FROM APPLICATION_AREA 
               WHERE APLCTN_AREA_NAME = 'Your Application Area Name' 
                 AND OPRTNL_FLAG = 'A'), 
             'N', 'A', 1, SYSDATE, 
             1, SYSDATE, 
             (SELECT LKP_VALUE_CODE 
                FROM LOOKUP_VALUE 
               WHERE LKP_VALUE_NAME = ' Your Module Name Pages' 
                 AND OPRTNL_FLAG = 'A'), 
             'Sample Page' 
            );  
INSERT INTO PAGE_X_ROLE 
            (PG_X_ROLE_SID, 
             PG_SID, 
             ROLE_SID, ACCESS_IND, OPRTNL_FLAG, 
             CREATED_BY, CREATED_DATE, MODIFIED_BY, MODIFIED_DATE 
            ) 
     VALUES (PAGE_X_ROLE_SEQ.NEXTVAL, 
             (SELECT PG_SID 
                FROM PAGE 
               WHERE PG_NAME = 'pgSamplePage' 
                     AND OPRTNL_FLAG = 'A'), 
             (SELECT ROLE_SID 
                FROM ROLE 
               WHERE ROLE_NAME = 'Super Role' AND OPRTNL_FLAG = 'A'), 3, 'A', 
             1, SYSDATE, 1, SYSDATE 
            );  
The Page SID value must fall within a specific range. This range can be derived from numbers: Application Area Sid+00000000 to Application Area Sid+99999999  For example: If your Application area sid value is 8, your page sid can range from 800000000 to 899999999. 
RBAC—Role Based Access Control

FQHC(Federally Qualified Health Center)
-------------------------------------------------------           
Overall rough concept: The area where medical facility is very poor that means no proper hospitals available only some private clinics available, those area people are eligible for FQHC facility.
Here State will pay some amount to that clinic for treatment of the people those are involved in Medicaid service. And clinic will serve the service based on these amount. If treatment amount is less than the given amount then these amount again back to state on next year and vice versa.
e.g.  State provide$50,000 to clinic on 15 jan 2015
        total expenditure of treatment amount=$30,000
       Clinic will return $20,000 back to state on 15 jan 2016.
canara
91919185--cu id
HZI0ZLHTWAY7---login  HZUVZLHTVAV7
transaction p---XAWLDWN3   XHWLDVN3
PUTTY Use:
Connecting to Linux from Windows by using PuTTY
After you have created a new cloud server with the control panel, your next step is to make a secure remote connection from your local computer to your cloud server.  This article describes how to use a client called PuTTY to form an Secure Shell (SSH) connection from a computer running a Microsoft Windows OS to a Linux server.

Subject: Steps to run the CNSICTI21 server: 

Server Name:  cnsicti21 /  10.86.24.51

User name: sdui
Password: Securecc123$

Tools required: Winscp / FileZilla, Putty.

Scripts Location : /app1/sdui/scripts (Utah_MCJbossStart.sh and Utah_MCJbossStop.sh)

Source Code: /app1/sdui/UTAH_MC

Jboss Path: /app1/sdui/jboss-5.0.1.GA/server/UTAH_MC

Steps to run:
1.	Copy the source code to /app1/sdui/UTAH_MC
2.	Open Putty
3.	Stop the server:
a.	Run the stop server scripts, 
i.	cd scripts/
ii.	./Utah_MCJbossStop.sh
 
4.	Do the build
a.	Go to the Source code folder,
i.	cd /app1/sdui/UTAH_MC/JavaSource/build
 

5.	Run the following scripts first
export ANT_HOME=/app1/sdui/apache-ant-1.7.0 
export ANT_OPTS="-Xmx256M" 
export PATH=${ANT_HOME}/bin:${JAVA_HOME}/bin:${PATH}

6.	Do the build,
a.	Ant clean all deploy
 

7.	After Build,
a.	Go to the scripts location and Start the server,
b.	Run the stop server scripts, 
i.	cd scripts/
ii.	./Utah_MCJbossStart.sh
 

8.	Check the URL.


Notes: Don’t change the properties, oracle-ds, folder locations etc.
Also, SVN is not yet enabled for UTAH_MC, so move the code manually using the Winscp/FileZilla.

PROVIDER

JIRA ACCESS:
https://cnsidefectsrepo.cns-inc.com:8443/login.jsp?permissionViolation=true&os_destination=%2Fbrowse%2FUTMMIS-4012

user name : guruswamyc
PWD : temp123

Remote desktop connection for UAT and SIT Testing
Mstsc  -----  10.14.11.102

UN-NarayanaswamiV
PWD-LA$tqtr2015

UAT URL--http://168.180.131.34:9000/uat/login.do



1.	To validate the NPI, use the following links, 
http://www.touchoftechnology.com/npi-luhn-check-digit-calculation/ 
http://debruinconsulting.com/npi.php

2.	Provider login credentials for DEV url, (http://10.14.11.41:9083/Dev/jsp/common/pgLogin.jsp )
Domain: saha37373510902 
User Name: saha3737a 
Password:  dshs123$
WA-MC-TRACK(05/09/2016)

Remote box (64.214.71.39) connection.
Credential same as system login credential.

URL: https://c5appvm.cns-inc.com/svn/providerone       SVN access path
DB Details for WA-MC-TRACK:


Tnsnames details.
 
wadev =
  (DESCRIPTION =
    (ADDRESS_LIST =
      (ADDRESS = (PROTOCOL = TCP)(HOST = 10.86.25.16)(PORT = 1521))
    )
    (CONNECT_DATA =
      (SERVICE_NAME =wadev)
    )
  )

Schema Credential:


Server /IP Address	Database Name	Version	Schema Name/Password	Project
10.86.25.16	wadev	11g	P1app/CTI#p1app#16	ProviderOne


ADA-compliant
The Department of Justice (DOJ) published the Americans with Disabilities Act (ADA) Standards for Accessible Design in September 2010. These standards state that all electronic and information technology must be accessible to people with disabilities.


E:\chitta \ MC_TRACK_PROJECT workspace

MCTrack Demo URL  - Bookmark this for your reference.

http://208.51.76.251:8180/wamctrack0517

User name: wa@state.gov
Password: walogin




Project path
\\cns-inc.com\cti\Public\kasi\mctrackSetupTool




Difference between jboss 5.1 and 7.1
Jboss5.1 contain configuration file as “oracle-ds.xml” and jboss7.1 contain standalone.xml




Note:
In MC_TRACK basically we place the raw data in staging table  then check the data and only valid data enter into business table.
ITF: Integration Testing Environment
WEBLOAD NOTES:
->In webload tool first we need to record the project. Each and every step we need to give start and end comments. In the end comment we need to write the comment in between the double quote. Then we edit the java script and run the project.
->to select the round(no of rotation) goto tools->setting->then give the number of rotation.
-> In record start step comment give normal and end comment give in between  double quote.

Query for updating user password
UPDATE TRN_MCTRACK_USER
   SET USER_PASSWORD = 'Tnr+vPuuAAsix8heVWD4mioCgLQ='
WHERE EMAIL_ID = '' –-Give your mail id here.

WEBLOAD CREDENTIAL:

URL: https://test.providerone.wa.gov/intgtst            (Providerone need to run remote 39 machine)
wlHttp.FormData["rfld_a:DomainNme"] = "DSHS"
wlHttp.FormData["rfld_a:UserID"] = "BhogiV"
wlHttp.FormData["nfld:UserPwd"] = "webload123$"  

ANS Hint: Qwer!2ty

DB Credential: ITF Environment

USERNAME:  P1APPLKP
PWD:  RfGKU7dbacAi
SID: OPSITF15_CMAN


To start and stop regression environment of webload
http://gdwacm03vm:9090/login?from=%2F
UserId: developer

Password: developer

1.	Below are the State/Worker user IDs for the Regression  Link - https://test.providerone.wa.gov/Automation

Domain	UserID	Password	User_Type
DSHS	PatchP	dshs123$	Worker
DSHS	BhogiVJ	dshs123$	Worker
DSHS	KotaK	dshs123$	Worker



Portal User IDs:

Domain	UserID	Password	User_Type
1046318	bobbij	test123$	Portal
1046318	kathys	test123$	Portal

We need to modify UseCase 63

Domain/UserID/Password

1013514/HopeJ/test123$
Select Profile: EXT Provider Super User

We need to modify UseCase 34

Domain/UserID/Password

1013514/HopeJ/test123$

Select Profile: EXT Provider Super User

UseCase38
Domain/User/Password: 1113863/TrofiN/dshs123$
Profile:

EXT View Provider Social Services




Automation portal credential
2006573                      JonesKL          auto123$ 




DB Details: Automation environment
        DB Details:  Schema/Password

P1APPLKP        QyCbdHS0eiHu   

AUTOREG_CMAN=
  (DESCRIPTION_LIST=
    (LOAD_BALANCE=on)
    (DESCRIPTION=
      (ADDRESS_LIST=
        (SOURCE_ROUTE=on)
        (ADDRESS=
          (PROTOCOL=TCP)
          (HOST=waivcman01.wa-mmis.pri)
          (PORT=1625)
        )
        (ADDRESS=
          (PROTOCOL=TCP)
          (HOST=waisc-scan.wa-mmis.pri)
          (PORT=1521)
        )
      )
      (CONNECT_DATA=
        (SERVICE_NAME=DVLPR_AUTOREG)
      )
    )
    (DESCRIPTION=
      (ADDRESS_LIST=
        (SOURCE_ROUTE=on)
        (ADDRESS=
          (PROTOCOL=TCP)
          (HOST=waivcman02.wa-mmis.pri)
          (PORT=1625)
        )
        (ADDRESS=
          (PROTOCOL=TCP)
          (HOST=waisc-scan.wa-mmis.pri)
          (PORT=1521)
        )
      )
      (CONNECT_DATA=
        (SERVICE_NAME=DVLPR_AUTOREG)
      )
    )
  )



Sanity Test:
sanity test is a very brief run-through of the functionality of a computer program, system, calculation, or other analysis, to assure that part of the system or methodology works roughly as expected.
MC_TRACK URL:
                http://localhost:8080/MCTrack
Credential for super user:
                Default UserName :  wa.mctrackadmin@cns-inc.com 
and        password   :  Admin    
Credential for user:
         UserName:chittaranjan.kar@cns-inc.com
         Password  :Admin

SMTP URL for MCTRACK:
url:  wa.mctrack.cntrctadmin@cns-inc.com

Path of mctrack project and document:
E:\CTI\users\kasi\CCSS\WA_Core_MCtrack_ITF\Core_MCTrack\Core_MCTrack\WA_Release_2.1\Configuration Tool

\\cns-inc.com\cti\Public\kasi\mctrackSetupTool

MCTrack Demo URL  - Bookmark this for your reference.

http://208.51.76.251:8180/wamctrack0517

User name: wa@state.gov
Password: walogin

Toad license:

4-02914-17995-10570-08095
 
Site Message:  WA STATE DEPARTMENT OF SOCIAL HEALTH SERVICES

Database Credential:

CTI Development 	WAMCTRACK_DEV	wamctrack_dev2#	10.86.24.2	1521	sdrulitT	 
WA MCTrack Development	P1APPMCT	Mju76yhn	 	 	 	ITFDEV_CMAN
WA MCTrack ITF	P1APPMCTLKP	phwertyc	 	 	 	OPSITF15_CMAN
WA MCTrack UAT	P1APPMCTLKP	nhy673rw54	 	 	 	OPSUAT15_CMAN
FTP details:
WA MCTrack DEV/ITF/UAT	10.4.3.66	devuser	abc@123
22	Dev Profile
 Log location :
/apps/IBM8.5/WebSphere/AppServer/profiles/fortify/logs/server1
WAR deployed folder :
/apps/IBM8.5/WebSphere/AppServer/profiles/fortify
/installedApps/waivwebapp02Node05Cell/MCTrack.ear

ITF Profile
 Log location :
/apps/IBM8.5/WebSphere/AppServer/profiles/ITF_MCTrack/logs/server1
WAR deployed folder :
/apps/IBM8.5/WebSphere/AppServer/profiles/ITF_MCTrack
/installedApps/waivwebapp02Node05Cell/MCTrack.ear

UAT Profile
 Log location :
/apps/IBM8.5/WebSphere/AppServer/profiles/UAT_MCTrack/logs/server1
WAR deployed folder :
/apps/IBM8.5/WebSphere/AppServer/profiles/UAT_MCTrack
/installedApps/waivwebapp02Node05Cell/MCTrack.ear
					
URL:
MCTrack Demo URL	http://208.51.76.251:8180/wamctrack0526
wa@state.gov
walogin
WA MCTrack Dev URL	https://10.4.3.66:20103/MCTrack/login
wa.mctrackamdin@cns-inc.com
Admin
WA MCTrack ITF URL	https://test.providerone.wa.gov/intgtstmct/
wa.mctrackamdin@cns-inc.com
Admin

Environment	URL	UserName	Password	
MCTrack Demo URL	http://208.51.76.251:8180/wamctrack0526
wa@state.gov
walogin	
WA MCTrack Dev URL	https://test.providerone.wa.gov/devmct
wa.mctrackadmin@cns-inc.com
Admin	
WA MCTrack ITF URL	https://test.providerone.wa.gov/intgtstmct
wa.mctrackadmin@cns-inc.com
Admin	
WA MCTrack UAT URL	https://test.providerone.wa.gov/uatmct
 	 	
WA MCTrack DEV Admin Console	https://10.4.3.66:20104/ibm/console/login.do
 	 	NO username and password
WA MCTrack ITF Admin Console	https://10.4.3.66:20153/ibm/console/login.do
 	 	NO username and password
WA MCTrack UAT Admin Console	https://10.4.3.66:20221/ibm/console/login.do
 	 	NO username and password
WA P1 PROD	P1APPLKP	P1APPLKP	 	 	 	PRONEPRD_CMAN

MCTrack onsite Dev environment URL:
https://test.providerone.wa.gov/devmct
Product portal Documentation link

http://208.51.76.228:8280/web/mc-track

USED DEFECT TRACKING SYSTEM
IBM - IBM Rational ClearQuest

Public folder access:   \\cns-inc.com\cti\Public\chitta

SMTP server in production

Server : prodmailhost.wa-mmis.pri
Port : 25

Please find below application URL’s for production. 

MCtrack2
http://waplwebapp02.wa-mmis.pri:9092/mct/login

MCtrack3
http://waplwebapp03.wa-mmis.pri:9087/mct/login

F5 url
https://www.providerone.was.gov/mct


R2 mctrack view .39 machine location
C:\Users\karc\WA_MCTrack_Core_Prod\MCTrack_Core\MCTrackCoreComp

ClearCase and ClearQuest Access
KarC
12345





SPOOL E:\CTI\USERS\KASI\MCTRACK\R2.1.5\A.LOG;
SHOW USER;
SET ECHO ON;
SET DEFINE OFF;
SET SERVEROUTPUT ON SIZE 400000;
SELECT TO_CHAR(SYSDATE,'DD-MON-YYYY HH24:MI:SS')START_TIME FROM DUAL;
@E:\CTI\users\kasi\MCTrack\R2.1.5\a.sql;
SELECT TO_CHAR(SYSDATE,'DD-MON-YYYY HH24:MI:SS')END_TIME FROM DUAL;
SPOOL OFF;

CTI:Center for Technology and Innovation
ETRR: Encounter Transaction Result Report

Please find the updated prefixes to reach any extension in the below mentioned US offices using “5 digit dialing” from CTI. 

For e.g. Rockville Corp office number 240-399-2013, dial 42013

Location	Prefix
Lansing – Millennium, Centennial  and 825 Office	2
Rockville – HQ	4
Olympia Office	7


ClearQuest URL:

https://cnsicqvm.cns-inc.com/cqweb/
arumugamv
arumugamv

KarC
12345

DEMO URL 25/08/2016

http://10.86.24.1:8280/UI/MC-Track/MC-Track-WA
State Portal –

Email: wa@state.gov
Password: walogin

Plan Portal - 

Email: waplan@gmail.com
Password: planlogin


Latest ITF MCTRACK credential
Username:Chittaranjan.kar@cns-inc.com
PWD:Mctrack@123

MCTRACK PROJECT SETUP IN SCREEN:

1-How to create the new user and map the user?
Click Admin->User Admin->user list->add new user
Table: TRN_MCTRACK_USER
User Mapping:
Configure Admin->Add new Group->Add User into new Group
Then User are able the see the report of particular plan where they mapped.
2-How to upload a contract?
Go to Contract Upload-> select program->select plan->upload a new contract->map the report and compliance measure->finish
3-After uploading contract how to add report?
go to home page-> select any plan->select timely submission-> view all details->Go to contract->repository->select report->add new report->then run the below procedure in DB -> then report show in submission report page.
-- execute this procedure to make the reports to open status from schedule
SET SERVEROUTPUT ON;
DECLARE
P_ERR_CODE NUMBER;
P_ERR_MSG VARCHAR2(4000 BYTE);
BEGIN
PRC_RPT_INSTNC_OPN(
    P_ERR_CODE => P_ERR_CODE,
            P_ERR_MSG => P_ERR_MSG
);
commit;
dbms_output.put_line('Error Message: ' || P_ERR_MSG);
END;
/ 
4-How to upload the report?
Goto submission-> submit/Resubmit Report->select any report->upload report->finish->Generate reference no

Search this reference no in submit Report tab and complete SAVE Flow.
S- SUBMISSION
A-ACKNOWLADGEMENT
V-VERIFICATION
E-EXECUTION

Table:
TRN_MCTRACK_USER-----User Info
TRN_CONTRACT----Plan Info







Spool Generation Shortcut

Steps:
1-Generate insert statement and Put data in SCR_DCR_TABLE table.

 

2-Create the folder Structure in source and log location.

3-After Populate the data in above table run the below procedure.
SET SERVEROUTPUT ON;
DECLARE
   V_FILEID_R            UTL_FILE.FILE_TYPE;
   V_FILEID_W            UTL_FILE.FILE_TYPE;
   V_DIR_NAME            VARCHAR2 (200) := 'ILNS_DEV_DIR';
   V_LOC_SQL_PATH VARCHAR2 (4000)
         := 'E:\CTI\users\kasi\CCSS\WA_MCTrack_Core_ITF\MCTrack_Core\MCTrackCoreComp\WA_Release_2.1.1\DB Objects\' ; 
         
   V_LOC_LOG_PATH VARCHAR2 (200) 
         := 'E:\CTI\users\kasi\CCSS\CTI_DEV_SYNC_LOGS\RELEASE 2.1.1\' ;  -- Change LOG folder directory path here
      V_LINE_CNT            NUMBER := 0;
   V_BUFFER              VARCHAR2 (32000);
   V_BUFFER1             VARCHAR2 (32000);
   V_QUERY               VARCHAR2 (32000);
BEGIN
   FOR K
   IN (  SELECT  *
           FROM   SCR_DCR_TABLE    -- Change table name here   
       ORDER BY   sno)
   LOOP
      BEGIN
         V_QUERY :=
               'SPOOL '
            || V_LOC_LOG_PATH
            || REPLACE (upper(K.FILE_NAME), '.SQL', '.LOG')
            || CHR (13)
            || CHR (10)
            || 'SHOW USER;'
            || CHR (13)
            || CHR (10)
            || 'SET ECHO ON;'
            || CHR (13)
            || CHR (10)
            || 'SET DEFINE OFF;'
            || CHR (13)
            || CHR (10)
            || 'SET SERVEROUTPUT ON SIZE 400000;'
            || CHR (13)
            || CHR (10)
            || 'SELECT TO_CHAR'
            || '('
            || 'SYSDATE,'
            || '''DD-MON-YYYY HH24'
            || ':'
            || 'MI'
            || ':'
            || 'SS'
            || ''')'
            || 'START_TIME FROM DUAL;'
            || CHR (13)
            || CHR (10)
            || '@'||V_LOC_SQL_PATH
            || K.FILE_NAME
            || ';'
            || CHR (13)
            || CHR (10)
            || 'SELECT TO_CHAR(SYSDATE,'
            || '''DD-MON-YYYY HH24'
            || ':'
            || 'MI'
            || ':'
            || 'SS'''
            || ')'
            || 'END_TIME FROM DUAL;'
            || CHR (13)
            || CHR (10)
            || 'SPOOL OFF;'
            || CHR (13)
            || CHR (10);
         V_LINE_CNT := V_LINE_CNT + 1;
      
    DBMS_OUTPUT.PUT_LINE (V_QUERY);
    DBMS_OUTPUT.PUT_LINE ('---------------------------------------------');
    END;

   END LOOP;
EXCEPTION
   WHEN UTL_FILE.INVALID_PATH
   THEN
      DBMS_OUTPUT.PUT_LINE ('INVALID PATH');
   WHEN NO_DATA_FOUND
   THEN
      UTL_FILE.FCLOSE (V_FILEID_R);
      NULL;
END;

Highlighted area of above procedure need to change based on your location.

Regular expression for Notepad++
------------------------------------------------    
^         # Start of line
([ \t]*)  # Match any number of spaces or tabs, capture them in group 1
\r?\n     # Match one linebreak
\s+       # Match any following whitespace
$         # until the last possible end of line.
\r?       # every individual Word

Getting all open defect in clear quest:
----------------------------------------------------
https://cnsicqvm.cns-inc.com/cqweb/restapi/8.0.0.1/cqpro/QUERY/34397280?format=HTML&noframes=true

MCTrack SVN path
https://c5appvm.cns-inc.com/svn/WA_MC_Track/Code/trunk/WA-MCTrack


