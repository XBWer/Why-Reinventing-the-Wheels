# Why-Reinventing-the-Wheel?
Replication package of the paper "**Why Reinventing the Wheel? An Empirical Study on Library Reuse and Re-implementation**".

## Abstract

Nowadays, with the rapid growth of open source software (OSS), library reuse becomes more and more popular since a large amount of third- party libraries are available to download and reuse. A deeper understanding on *why* developers reuse a library (i.e., replacing self-implemented code with an external library) or re-implement a library (i.e., replacing an imported external library with self-implemented code) could help researchers better understand the factors that developers are concerned with when reusing code. This understanding can then be used to improve existing libraries and API recommendation tools for researchers and practitioners by using the developers concerns identified in this study as design criteria.

In this work, we investigated the reasons behind library reuse and re-implementation. To achieve this goal, we first crawled data from two popular sources, F-Droid and GitHub. Then, potential instances of library reuse and re-implementation were found automatically based on certain heuristics. Next, for each instance, we further manually identified whether it is valid or not. For library re-implementation, we obtained 82 instances which are distributed in 75 repositories. We then conducted two types of surveys (i.e., individual survey to corresponding developers of the validated instances and another open survey) for library reuse and re-implementation. For library reuse individual survey, we received 36 responses out of 139 contacted developers. For re-implementation individual survey, we received 13 responses out of 71 contacted developers. In addition, we received 56 responses from the open survey. Finally, we perform qualitative and quantitative analysis on the survey responses and commit logs of the validated instances.

The results suggest that library reuse occurs mainly because developers were initially unaware of the library or the library had not been introduced. Re-implementation occurs mainly because the used library method is only a small part of the library, the library dependencies are too complicated, or the library method is deprecated. Finally, based on all findings obtained from analyzing the surveys and commit messages, we provided a few suggestions to improve the current library recommendation systems: tailored recommendation according to users' preferences, detection of external code that is similar to a part of the users' code (to avoid duplication or re-implementation), grouping similar recommendations for developers to compare and select the one they prefer, and disrecommendation of poor-quality libraries.

## Suggestions for researchers and practitioners

- **Tailored recommendation**: Since developers may have their own preferenceof reusing libraries, the system can study and collect users’ preference before giving them suggestions. For example, the system can analyze all external libraries used by a developer in her current and past projects, use machine-learning algorithms to classify these libraries according to the do-main or requirement of this developer, and use these information to makebetter recommendations.
- **Detection of similar solution**: The system can search for a piece of codethat has similar functionality to a part of the project (e.g., a method, class,module). An early suggestion of library reuse potential can prevent developers from reinventing the wheel. Earlier approaches have already been capable of detecting re-implementation of a piece of library code if the library has already been used in the project. However, developers might also want to prevent re-implementations of the code from unused libraries. In such case, semantic analysis and clone detection techniques canhelp to search similar code snippets.
- **Grouped recommendations**: The system can group similar recommendations for developers to compare and select the library they prefer. In sucha group, the system can further rank the the recommendations based ontheir number of users, reviews, and documentation quality.
- **Display of libraries’ characteristics**: This can help to quickly assess thequality of a library. As aforementioned, when there are multiple candidates, the system can also use this information to rank the recommendations. For example, when a developer wants to install a plugin from Eclipse Marketplace, a summary of the plugin will be provided. Likewise, when adeveloper imports a new external library, the recommendation system can pop up a summary window, showing characteristics of the library.
- **Disrecommendation**: As we have learned, replacing a deprecated or inactivelibrary is one of the reasons why developers switched from library reuseto reimplementation. If an imported library is deprecated, obsolete, badlyrated, or inactively maintained, a library recommendation tool may wantto suggest developers to replace the library with an alternative library. For example, a disrecommendation system can scan all imported external libraries and connect to the libraries’ website, checking whether any libraryis deprecated or out of maintenance. If so, the system will warn developersto avoid this library and provide detailed reasons on why they should do so.A future recommendation systems may also predict deprecation or futureissues (more generally) with some libraries and pro-actively recommend alternatives.
- **License compatibility suggestion**: To help software organizations avoid license violations, library recommendations tools can also detect the licenseof the recommended library, comparing it with the license of developers’ home project, checking whether the recommended library can be legallyimported.
