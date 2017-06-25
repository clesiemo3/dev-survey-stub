---
title: "2017 Developer Survey Stub"
author: 'clesiemo3'
date: '2017-06-25'
output: html_document
---

Sourced from https://github.com/dgrtwo/tabs-spaces-post


```r
df <- read.csv("developer_survey_2017/survey_results_public.csv")
head(df)
```

```
##   Respondent                                         Professional
## 1          1                                              Student
## 2          2                                              Student
## 3          3                               Professional developer
## 4          4 Professional non-developer who sometimes writes code
## 5          5                               Professional developer
## 6          6                                              Student
##                ProgramHobby        Country     University
## 1                 Yes, both  United States             No
## 2                 Yes, both United Kingdom Yes, full-time
## 3                 Yes, both United Kingdom             No
## 4                 Yes, both  United States             No
## 5 Yes, I program as a hobby    Switzerland             No
## 6                 Yes, both    New Zealand Yes, full-time
##                         EmploymentStatus
## 1 Not employed, and not looking for work
## 2                     Employed part-time
## 3                     Employed full-time
## 4                     Employed full-time
## 5                     Employed full-time
## 6 Not employed, and not looking for work
##                                                     FormalEducation
## 1                                                  Secondary school
## 2 Some college/university study without earning a bachelor's degree
## 3                                                 Bachelor's degree
## 4                                                   Doctoral degree
## 5                                                   Master's degree
## 6                                                  Secondary school
##                                  MajorUndergrad
## 1                                          <NA>
## 2      Computer science or software engineering
## 3      Computer science or software engineering
## 4 A non-computer-focused engineering discipline
## 5      Computer science or software engineering
## 6                                          <NA>
##                                                HomeRemote
## 1                                                    <NA>
## 2                   More than half, but not all, the time
## 3 Less than half the time, but at least one day each week
## 4 Less than half the time, but at least one day each week
## 5                                                   Never
## 6                                                    <NA>
##                CompanySize
## 1                     <NA>
## 2       20 to 99 employees
## 3 10,000 or more employees
## 4 10,000 or more employees
## 5       10 to 19 employees
## 6                     <NA>
##                                                             CompanyType
## 1                                                                  <NA>
## 2                   Privately-held limited company, not in startup mode
## 3                                           Publicly-traded corporation
## 4 Non-profit/non-governmental organization or private school/university
## 5                   Privately-held limited company, not in startup mode
## 6                                                                  <NA>
##       YearsProgram    YearsCodedJob YearsCodedJobPast
## 1     2 to 3 years             <NA>              <NA>
## 2    9 to 10 years             <NA>              <NA>
## 3 20 or more years 20 or more years              <NA>
## 4   14 to 15 years    9 to 10 years              <NA>
## 5 20 or more years   10 to 11 years              <NA>
## 6     6 to 7 years             <NA>              <NA>
##                                                            DeveloperType
## 1                                                                   <NA>
## 2                                                                   <NA>
## 3                                                                  Other
## 4                                                                   <NA>
## 5 Mobile developer; Graphics programming; Desktop applications developer
## 6                                                                   <NA>
##   WebDeveloperType MobileDeveloperType NonDeveloperType CareerSatisfaction
## 1             <NA>                <NA>             <NA>                 NA
## 2             <NA>                <NA>             <NA>                 NA
## 3             <NA>                <NA>             <NA>                  8
## 4             <NA>                <NA>   Data scientist                  6
## 5             <NA>                <NA>             <NA>                  6
## 6             <NA>                <NA>             <NA>                 NA
##   JobSatisfaction ExCoderReturn ExCoderNotForMe ExCoderBalance
## 1              NA          <NA>            <NA>           <NA>
## 2              NA          <NA>            <NA>           <NA>
## 3               9          <NA>            <NA>           <NA>
## 4               3          <NA>            <NA>           <NA>
## 5               8          <NA>            <NA>           <NA>
## 6              NA          <NA>            <NA>           <NA>
##   ExCoder10Years ExCoderBelonged ExCoderSkills ExCoderWillNotCode
## 1           <NA>            <NA>          <NA>               <NA>
## 2           <NA>            <NA>          <NA>               <NA>
## 3           <NA>            <NA>          <NA>               <NA>
## 4           <NA>            <NA>          <NA>               <NA>
## 5           <NA>            <NA>          <NA>               <NA>
## 6           <NA>            <NA>          <NA>               <NA>
##   ExCoderActive                 PronounceGIF ProblemSolving BuildingThings
## 1          <NA> With a soft "g," like "jiff" Strongly agree Strongly agree
## 2          <NA> With a hard "g," like "gift"           <NA>           <NA>
## 3          <NA> With a hard "g," like "gift" Strongly agree Strongly agree
## 4          <NA> With a soft "g," like "jiff" Strongly agree Strongly agree
## 5          <NA> With a soft "g," like "jiff"           <NA>           <NA>
## 6          <NA> With a hard "g," like "gift"           <NA>           <NA>
##   LearningNewTech  BoringDetails    JobSecurity DiversityImportant
## 1           Agree       Disagree Strongly agree              Agree
## 2            <NA>           <NA>           <NA>               <NA>
## 3  Strongly agree Somewhat agree          Agree     Strongly agree
## 4  Strongly agree       Disagree Somewhat agree              Agree
## 5            <NA>           <NA>           <NA>               <NA>
## 6            <NA>           <NA>           <NA>               <NA>
##   AnnoyingUI FriendsDevelopers  RightWrongWay UnderstandComputers
## 1      Agree          Disagree Somewhat agree            Disagree
## 2       <NA>              <NA>           <NA>                <NA>
## 3      Agree    Somewhat agree       Disagree            Disagree
## 4      Agree             Agree Somewhat agree   Strongly disagree
## 5       <NA>              <NA>           <NA>                <NA>
## 6       <NA>              <NA>           <NA>                <NA>
##      SeriousWork InvestTimeTools       WorkPayCare KinshipDevelopers
## 1 Strongly agree  Strongly agree Strongly disagree             Agree
## 2           <NA>            <NA>              <NA>              <NA>
## 3          Agree  Somewhat agree          Disagree    Somewhat agree
## 4 Strongly agree           Agree          Disagree    Strongly agree
## 5           <NA>            <NA>              <NA>              <NA>
## 6           <NA>            <NA>              <NA>              <NA>
##   ChallengeMyself   CompetePeers ChangeWorld
## 1           Agree       Disagree       Agree
## 2            <NA>           <NA>        <NA>
## 3           Agree       Disagree       Agree
## 4  Strongly agree Somewhat agree       Agree
## 5            <NA>           <NA>        <NA>
## 6            <NA>           <NA>        <NA>
##                                               JobSeekingStatus
## 1 I'm not actively looking, but I am open to new opportunities
## 2                                                         <NA>
## 3                                                         <NA>
## 4                              I am actively looking for a job
## 5                                                         <NA>
## 6 I'm not actively looking, but I am open to new opportunities
##   HoursPerWeek                LastNewJob  AssessJobIndustry
## 1            0     Not applicable/ never     Very important
## 2           NA                      <NA>               <NA>
## 3           NA                      <NA>               <NA>
## 4            5 Between 2 and 4 years ago Somewhat important
## 5           NA                      <NA>               <NA>
## 6            0     Not applicable/ never          Important
##        AssessJobRole       AssessJobExp  AssessJobDept      AssessJobTech
## 1     Very important          Important Very important     Very important
## 2               <NA>               <NA>           <NA>               <NA>
## 3               <NA>               <NA>           <NA>               <NA>
## 4 Somewhat important Somewhat important      Important          Important
## 5               <NA>               <NA>           <NA>               <NA>
## 6 Somewhat important          Important      Important Somewhat important
##    AssessJobProjects AssessJobCompensation    AssessJobOffice
## 1     Very important             Important     Very important
## 2               <NA>                  <NA>               <NA>
## 3               <NA>                  <NA>               <NA>
## 4     Very important             Important     Very important
## 5               <NA>                  <NA>               <NA>
## 6 Somewhat important             Important Somewhat important
##   AssessJobCommute    AssessJobRemote     AssessJobLeaders
## 1   Very important     Very important       Very important
## 2             <NA>               <NA>                 <NA>
## 3             <NA>               <NA>                 <NA>
## 4        Important Somewhat important   Not very important
## 5             <NA>               <NA>                 <NA>
## 6        Important Somewhat important Not at all important
##   AssessJobProfDevel AssessJobDiversity   AssessJobProduct
## 1     Very important Somewhat important Not very important
## 2               <NA>               <NA>               <NA>
## 3               <NA>               <NA>               <NA>
## 4     Very important          Important     Very important
## 5               <NA>               <NA>               <NA>
## 6 Somewhat important Somewhat important Somewhat important
##    AssessJobFinances
## 1 Somewhat important
## 2               <NA>
## 3               <NA>
## 4     Very important
## 5               <NA>
## 6 Not very important
##                                                         ImportantBenefits
## 1                        Stock options; Vacation/days off; Remote options
## 2                                                                    <NA>
## 3                                                                    <NA>
## 4 Stock options; Annual bonus; Health benefits; Equipment; Private office
## 5                                                                    <NA>
## 6                                  Vacation/days off; Expected work hours
##   ClickyKeys      JobProfile ResumePrompted
## 1        Yes           Other           <NA>
## 2         No           Other           <NA>
## 3        Yes            <NA>           <NA>
## 4        Yes LinkedIn; Other           <NA>
## 5       <NA>            <NA>           <NA>
## 6        Yes            <NA>           <NA>
##                                          LearnedHiring
## 1                                                 <NA>
## 2                                       Some other way
## 3                                                 <NA>
## 4 A friend, family member, or former colleague told me
## 5                                                 <NA>
## 6                                                 <NA>
##   ImportantHiringAlgorithms ImportantHiringTechExp
## 1                 Important              Important
## 2                 Important              Important
## 3                      <NA>                   <NA>
## 4        Somewhat important     Somewhat important
## 5                      <NA>                   <NA>
## 6        Not very important     Not very important
##   ImportantHiringCommunication ImportantHiringOpenSource
## 1                    Important        Somewhat important
## 2                    Important                 Important
## 3                         <NA>                      <NA>
## 4               Very important            Very important
## 5                         <NA>                      <NA>
## 6           Not very important                 Important
##   ImportantHiringPMExp ImportantHiringCompanies ImportantHiringTitles
## 1            Important       Not very important    Not very important
## 2   Somewhat important       Somewhat important    Not very important
## 3                 <NA>                     <NA>                  <NA>
## 4   Somewhat important       Somewhat important    Not very important
## 5                 <NA>                     <NA>                  <NA>
## 6   Not very important       Not very important    Not very important
##   ImportantHiringEducation   ImportantHiringRep
## 1     Not at all important   Somewhat important
## 2       Somewhat important   Not very important
## 3                     <NA>                 <NA>
## 4       Not very important            Important
## 5                     <NA>                 <NA>
## 6       Not very important Not at all important
##   ImportantHiringGettingThingsDone                    Currency
## 1                   Very important                        <NA>
## 2                   Very important British pounds sterling (£)
## 3                             <NA> British pounds sterling (£)
## 4                   Very important                        <NA>
## 5                             <NA>                        <NA>
## 6               Not very important                        <NA>
##                         Overpaid TabsSpaces EducationImportant
## 1                           <NA>       Tabs               <NA>
## 2                           <NA>     Spaces               <NA>
## 3 Neither underpaid nor overpaid     Spaces Not very important
## 4                           <NA>     Spaces               <NA>
## 5                           <NA>       <NA>               <NA>
## 6                           <NA>       Both               <NA>
##                                                          EducationTypes
## 1                              Online course; Open source contributions
## 2      Online course; Self-taught; Hackathon; Open source contributions
## 3 Self-taught; Coding competition; Hackathon; Open source contributions
## 4                                                                  <NA>
## 5                                                                  <NA>
## 6                     Self-taught; Hackathon; Open source contributions
##                                                                                                                                                     SelfTaughtTypes
## 1                                                                                                                                                              <NA>
## 2                                                                                                                 Official documentation; Stack Overflow Q&A; Other
## 3 Official documentation; Trade book; Textbook; Stack Overflow Q&A; Non-Stack online communities; Company internal community; Friends network; Built-in help; Other
## 4                                                                                                                                                              <NA>
## 5                                                                                                                                                              <NA>
## 6                                                                           Official documentation; Stack Overflow Q&A; Non-Stack online communities; Built-in help
##   TimeAfterBootcamp CousinEducation WorkStart
## 1              <NA>            <NA>   6:00 AM
## 2              <NA>            <NA>  10:00 AM
## 3              <NA>            <NA>   9:00 AM
## 4              <NA>            <NA>   9:00 AM
## 5              <NA>            <NA>      <NA>
## 6              <NA>            <NA>  10:00 AM
##              HaveWorkedLanguage
## 1                         Swift
## 2 JavaScript; Python; Ruby; SQL
## 3             Java; PHP; Python
## 4        Matlab; Python; R; SQL
## 5                          <NA>
## 6         JavaScript; PHP; Rust
##                                     WantWorkLanguage HaveWorkedFramework
## 1                                              Swift                <NA>
## 2                            Java; Python; Ruby; SQL           .NET Core
## 3                                    C; Python; Rust                <NA>
## 4                             Matlab; Python; R; SQL               React
## 5                                               <NA>                <NA>
## 6 Clojure; Elixir; Erlang; Haskell; Rust; TypeScript                <NA>
##        WantWorkFramework                        HaveWorkedDatabase
## 1                   <NA>                                      <NA>
## 2              .NET Core                             MySQL; SQLite
## 3                   <NA>                                     MySQL
## 4 Hadoop; Node.js; React MongoDB; Redis; SQL Server; MySQL; SQLite
## 5                   <NA>                                      <NA>
## 6                   <NA>                                     MySQL
##                            WantWorkDatabase
## 1                                      <NA>
## 2                             MySQL; SQLite
## 3                                      <NA>
## 4 MongoDB; Redis; SQL Server; MySQL; SQLite
## 5                                      <NA>
## 6                                      <NA>
##                                                  HaveWorkedPlatform
## 1                                                               iOS
## 2                                         Amazon Web Services (AWS)
## 3                                                              <NA>
## 4 Windows Desktop; Linux Desktop; Mac OS; Amazon Web Services (AWS)
## 5                                                              <NA>
## 6                          Linux Desktop; Amazon Web Services (AWS)
##                                                    WantWorkPlatform
## 1                                                               iOS
## 2            Linux Desktop; Raspberry Pi; Amazon Web Services (AWS)
## 3                                                              <NA>
## 4 Windows Desktop; Linux Desktop; Mac OS; Amazon Web Services (AWS)
## 5                                                              <NA>
## 6                                                     Linux Desktop
##                                                                                   IDE
## 1                                                                         Atom; Xcode
## 2          Atom; Notepad++; Vim; PyCharm; RubyMine; Visual Studio; Visual Studio Code
## 3                                                         Sublime Text; Vim; IntelliJ
## 4 Notepad++; Sublime Text; TextMate; Vim; IPython / Jupyter; NetBeans; PyCharm; Xcode
## 5                                                                                <NA>
## 6                                                                          Emacs; Vim
##                                            AuditoryEnvironment
## 1                                           Turn on some music
## 2 Put on some ambient sounds (e.g. whale songs, forest sounds)
## 3                                           Turn on some music
## 4                                           Turn on some music
## 5                                                         <NA>
## 6                                           Turn on some music
##                                 Methodology VersionControl
## 1                                      <NA>           <NA>
## 2                                      <NA>            Git
## 3 Agile; Lean; Scrum; Extreme; Pair; Kanban      Mercurial
## 4                                     Agile            Git
## 5                                      <NA>           <NA>
## 6                                      <NA>            Git
##            CheckInCode         ShipIt OtherPeoplesCode ProjectManagement
## 1                 <NA>           <NA>             <NA>              <NA>
## 2 Multiple times a day          Agree         Disagree Strongly disagree
## 3 Multiple times a day          Agree         Disagree          Disagree
## 4 Multiple times a day Somewhat agree            Agree    Somewhat agree
## 5                 <NA>           <NA>             <NA>              <NA>
## 6   A few times a week           <NA>             <NA>              <NA>
##   EnjoyDebugging      InTheZone DifficultCommunication CollaborateRemote
## 1           <NA>           <NA>                   <NA>              <NA>
## 2          Agree Somewhat agree               Disagree Strongly disagree
## 3          Agree          Agree               Disagree    Somewhat agree
## 4 Somewhat agree Strongly agree               Disagree    Somewhat agree
## 5           <NA>           <NA>                   <NA>              <NA>
## 6          Agree Strongly agree                   <NA>             Agree
##                                                                                   MetricAssess
## 1                                                                                         <NA>
## 2                         Customer satisfaction; On time/in budget; Peers' rating; Self-rating
## 3 Customer satisfaction; Benchmarked product performance; Manager's rating; Self-rating; Other
## 4                                                                                         <NA>
## 5                                                                                         <NA>
## 6                                                                                         <NA>
##   EquipmentSatisfiedMonitors EquipmentSatisfiedCPU EquipmentSatisfiedRAM
## 1         Somewhat satisfied    Not very satisfied  Not at all satisfied
## 2         Not very satisfied             Satisfied             Satisfied
## 3             Very satisfied    Somewhat satisfied             Satisfied
## 4                       <NA>                  <NA>                  <NA>
## 5                  Satisfied             Satisfied             Satisfied
## 6                       <NA>                  <NA>                  <NA>
##   EquipmentSatisfiedStorage EquipmentSatisfiedRW  InfluenceInternet
## 1            Very satisfied            Satisfied Not very satisfied
## 2                 Satisfied   Somewhat satisfied          Satisfied
## 3                 Satisfied   Somewhat satisfied     Very satisfied
## 4                      <NA>                 <NA>               <NA>
## 5                 Satisfied            Satisfied          Satisfied
## 6                      <NA>                 <NA>               <NA>
##   InfluenceWorkstation   InfluenceHardware    InfluenceServers
## 1                 <NA>                <NA>                <NA>
## 2  No influence at all No influence at all No influence at all
## 3   A lot of influence      Some influence      Some influence
## 4                 <NA>                <NA>                <NA>
## 5                 <NA>                <NA>                <NA>
## 6                 <NA>                <NA>                <NA>
##    InfluenceTechStack   InfluenceDeptTech   InfluenceVizTools
## 1                <NA>                <NA>                <NA>
## 2 No influence at all No influence at all No influence at all
## 3      Some influence  A lot of influence      Some influence
## 4                <NA>                <NA>                <NA>
## 5                <NA>                <NA>                <NA>
## 6                <NA>                <NA>                <NA>
##     InfluenceDatabase      InfluenceCloud InfluenceConsultants
## 1                <NA>                <NA>                 <NA>
## 2 No influence at all No influence at all  No influence at all
## 3      Some influence      Some influence       Some influence
## 4                <NA>                <NA>                 <NA>
## 5                <NA>                <NA>                 <NA>
## 6                <NA>                <NA>                 <NA>
##   InfluenceRecruitment InfluenceCommunication
## 1                 <NA>                   <NA>
## 2  No influence at all    No influence at all
## 3       Some influence         Some influence
## 4                 <NA>                   <NA>
## 5                 <NA>                   <NA>
## 6                 <NA>                   <NA>
##                                                           StackOverflowDescribes
## 1                       I have created a CV or Developer Story on Stack Overflow
## 2                       I have created a CV or Developer Story on Stack Overflow
## 3                       I have created a CV or Developer Story on Stack Overflow
## 4                       I have created a CV or Developer Story on Stack Overflow
## 5                                                                           <NA>
## 6 I have a login for Stack Overflow, but haven't created a CV or Developer Story
##   StackOverflowSatisfaction
## 1                         9
## 2                         8
## 3                         8
## 4                        10
## 5                        NA
## 6                         6
##                                          StackOverflowDevices
## 1                                            Desktop; iOS app
## 2 Desktop; iOS browser; iOS app; Android browser; Android app
## 3                               Desktop; iOS browser; iOS app
## 4                               Desktop; iOS browser; iOS app
## 5                                                        <NA>
## 6                       Desktop; iOS browser; Android browser
##   StackOverflowFoundAnswer StackOverflowCopiedCode StackOverflowJobListing
## 1  At least once each week     Haven't done at all           Once or twice
## 2            Several times           Several times           Once or twice
## 3            Once or twice     Haven't done at all     Haven't done at all
## 4  At least once each week           Several times At least once each week
## 5                     <NA>                    <NA>                    <NA>
## 6            Several times     Haven't done at all     Haven't done at all
##   StackOverflowCompanyPage  StackOverflowJobSearch
## 1      Haven't done at all     Haven't done at all
## 2            Once or twice           Once or twice
## 3      Haven't done at all     Haven't done at all
## 4            Several times At least once each week
## 5                     <NA>                    <NA>
## 6      Haven't done at all     Haven't done at all
##   StackOverflowNewQuestion    StackOverflowAnswer   StackOverflowMetaChat
## 1            Several times          Several times           Once or twice
## 2      Haven't done at all          Several times At least once each week
## 3      Haven't done at all At least once each day  At least once each day
## 4            Several times At least once each day  At least once each day
## 5                     <NA>                   <NA>                    <NA>
## 6      Haven't done at all    Haven't done at all     Haven't done at all
##   StackOverflowAdsRelevant StackOverflowAdsDistracting
## 1           Somewhat agree           Strongly disagree
## 2                 Disagree           Strongly disagree
## 3                 Disagree                    Disagree
## 4                    Agree           Strongly disagree
## 5                     <NA>                        <NA>
## 6                     <NA>                        <NA>
##   StackOverflowModeration StackOverflowCommunity StackOverflowHelpful
## 1       Strongly disagree         Strongly agree                Agree
## 2       Strongly disagree         Strongly agree                Agree
## 3       Strongly disagree         Strongly agree                Agree
## 4       Strongly disagree         Strongly agree       Strongly agree
## 5                    <NA>                   <NA>                 <NA>
## 6                   Agree      Strongly disagree                Agree
##   StackOverflowBetter StackOverflowWhatDo StackOverflowMakeMoney Gender
## 1      Strongly agree      Strongly agree      Strongly disagree   Male
## 2      Strongly agree      Strongly agree      Strongly disagree   Male
## 3               Agree               Agree               Disagree   Male
## 4               Agree      Strongly agree               Disagree   Male
## 5                <NA>                <NA>                   <NA>   <NA>
## 6      Strongly agree               Agree               Disagree   <NA>
##   HighestEducationParents                         Race        SurveyLong
## 1             High school White or of European descent Strongly disagree
## 2       A master's degree White or of European descent    Somewhat agree
## 3   A professional degree White or of European descent    Somewhat agree
## 4       A doctoral degree White or of European descent             Agree
## 5                    <NA>                         <NA>              <NA>
## 6     A bachelor's degree White or of European descent          Disagree
##   QuestionsInteresting QuestionsConfusing InterestedAnswers Salary
## 1       Strongly agree           Disagree    Strongly agree     NA
## 2       Somewhat agree           Disagree    Strongly agree     NA
## 3                Agree           Disagree             Agree 113750
## 4                Agree     Somewhat agree    Strongly agree     NA
## 5                 <NA>               <NA>              <NA>     NA
## 6                Agree           Disagree             Agree     NA
##   ExpectedSalary
## 1             NA
## 2          37500
## 3             NA
## 4             NA
## 5             NA
## 6             NA
```

Create your README.md for your own repository with `knitr::knit("README.Rmd")`
