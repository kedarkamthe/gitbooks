# Limitations of Monolithic Apps



* **Language/Framework lock:** Since entire application is written in single tech stack. Can’ t experiment with emerging technologies.
* **Difficult to Digest:** Once the app becomes large it becomes difficult for a developer to understand such a large codebase.
* **Difficult to distribute API development:** It becomes extremely difficult to do agile development and a large part of the developer’s time is wasted in resolving conflicts.
* **Deployment as a single unit:** Cannot independently deploy a single change to a single component. Changes are “held hostage” by other changes.
* **Development slows down:** I’ve worked on a codebase which had more than 50,000 classes. The sheer size of the codebase was enough to slow down the IDE and startup times due to which productivity used to suffer.
* **Resources are not optimized:** Some module might implement CPU-intensive image processing logic requiring compute-optimized instances and another module might be an in-memory database and best suited for Memory-optimized instances. But we’ll have to compromise on our choice of hardware. It might also happen that one module of application requires scaling but we’ll have to run an entire instance of the application again because we can’t scale a module individually.
