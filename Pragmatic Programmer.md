# Chapter 1 - A Pragmatic Philosophy:

*  Cat ate my source code
    * Take responsibility: When you accept responsibility for an outcome and if outcome is not in your favor don’t blame it on anyone and own the outcome. “Provide options, don’t make lame excuses”, have contingency plan. Before approaching someone on why can’t be done, talk to yourself about how does it sound, and how will it sound to your boss, explore possible options which they might offer beforehand.

*   Software Entropy: Entropy refers to amount of disorder in system. When it increases in software it leads to “software rot”. “Don’t live with Broken windows”.
    * Putting out fires: If you’re on a team with a project which is well designed, with well written and documented code, you will take extra measures to make changes just like the firefighters rolling out the mat to not mess up the expensive rug before putting out the fire.

* Stone soup and Boiled Frogs: Emulate the soldiers when you’re in a situation where you know what needs to be done and how to do it and there is a lot of red tape to get around. Be a catalyst for change as people find it easier to be a part of ongoing success.
    * On Villagers’ side: Remember the big picture otherwise it will be easy for people to deceive you gently and gradually.

* Good-Enough Software Involve the users in deciding what you’ve produced is good enough for them and ensure they’re happy. Make quality a requirement issue neither every software needs a space-shuttle accuracy nor it needs to be written sloppily. Let the user decide what he wants by making quality also a requirement.

* Know when to Stop Don’t spoil a perfectly good program by over-refinement.

* Knowledge Portfolio: Manage your “Knowledge Portfolio” like you manage your “Financial Portfolio”.
    * Invest Regularly as a habit even if its smaller amount. It will yield larger returns over time.
    * Diversification of your knowledge increases your value as a balance know ins-and-outs of technology you’re currently working on but don’t just stop there.
    * Manage Risk by investing in various technologies don’t always play safe.
    * Buy Low Sell High: Find and learn emerging technology, though it’s risky, returns pay off handsomely.
    * Review and rebalance: Because the industry is dynamic, keep revisiting your technology and reposition your Knowledge Portfolio as per market.
    * Goals
        * Learn at least one new language every year.
        * Read at least one technical book every quarter.
        * Participate in local user groups - Isolation jeopardizes your career.
        * Experiment with different environments.
        * Stay current.
    * Critical Thinking: Don’t believe everything you see on the web, see if its media hype, before investing.
* Communicate No matter how pragmatic you are, if you can’t effectively communicate your ideas, your thinking is sterile.
    * Be it a formal memo, document or a conference call, have an outline, Know what do you want to say. If your outline doesn’t seem to get the point across, refine your outline till it does.
    * Know your audience and communicate appropriately to suit their needs, not everyone wants to know every technical nitty-grit.
    * Choose your right moment and style to communicate to the audience. Ask when in doubt.
    * Make sure your documents are clean and look good.
    * Be a listener

# Chapter 2 - A Pragmatic Approach:

* Evils of Duplication: As programmers we collect, organize, maintain and harness knowledge in different forms. Maintenance as most of us believe is not a discrete activity which start post production, it is an ongoing process whether we are in design or implementation phase. The moment our understanding of something changes, we correct the knowledge capsule embedded in application, in doing so, it is easy to duplicate knowledge which causes a maintenance nightmare. We should always have a single unambiguous, authoritative representation of information within a system aka DRY. Below are the reasons for duplication,
    * Imposed duplication: Duplication is forced, because of documentation or library/coding restrictions. In case the project demands multiple representation of information because we are using more than one programming language and the same structure is shared across multiple layers of the application. It’s usually a good idea to use some sort of code generation tool which is capable of generating code across multiple layers of the application depending on some sort of metadata, and the information is only maintained once i.e. in metadata. Similarly Documentation in code can also cause duplication if it is not high-level enough, however it is always important to make sure that the code update and documentation update always go hand-in-hand.
    * Inadvertent duplication: Duplication as a result of mistakes in design. For example, if we have two entities Truck and DeliveryRoute and they both have Driver information as a part of them, when it is time to update the driver, because of duplication it is not quite obvious to know which entity to update. In such cases, we can have a third independent entity which knits both of these to the Driver information. Similarly unless the information needs to be cached for performance reasons, we don’t need to have representation of a separate piece of information which can be derived from existing information. For example: length of a line can be derived from start and end coordinates of a line.
    * Impatient duplication: Impatient duplication is caused as a result of impatience due to pressure. Discipline and willingness to spend a little time now to save quite a lot later can avoid impatient duplication.
    * Inter-developer duplication: Duplication occurring between different developers of the project. Example: U.S. State Governmental computer systems had 10,000 implementations of SSN validations. Best way to deal with this is to encourage communication between developers, forums to discuss common problems. Encouraging code reviewing is also a good practice.
* Orthogonality: is a term derived from geometry which essentially means, two or more things are independent of changes in one another. In a well designed system DB changes will not affect UI and vice versa. Non-orthogonal systems are inherently complex to change and control. Eliminate effects between unrelated things by designing components which are self-contained (independent and have a single, well defined purpose) aka cohesive in nature. Cohesive systems,
        * Increase productivity by,
            * reducing development and testing time.
            * promoting component re-use
        * Reduce risk by,
            * isolated diseased sections of code
            * making the resulting system less fragile
    * Project Teams: Project teams which are orthogonal are more efficient, one way to achieve orthogonality when it comes to teams is by separating infrastructure from application, and each infrastructure gets it’s own sub-team. Further more, application can be further divided on functionality.
    * Design: Designed software should be orthogonal in nature, one way to test if the existing software for orthogonality is to ask yourself “If I dramatically change the requirement behind a particular function, how many modules will be affected?”, if the answer is more than one then the application is not orthogonal. Orthogonality can be achieved with application of paradigms such as MVC. Another suggestion is to not design your application around properties which are not directly under your control.
    * Toolkits and Libraries: Choose your technologies wisely. If your choice of technology is not transparent and imposes restrictions on how objects should be created. The toolkits introduced should be akin to AOP, where one can introduce crosscutting concerns such as logging without changing the existing code.
    * Coding: 
        * Write shy code: Follow the law of Demeter
        * Avoid global data
        * Avoid similar functions: If they only differ in central algorithm refactor using Strategy Pattern or using Lambdas.
    * Testing: 
        * An orthogonally designed system is easy to test since interfaces to modules are independent and well defined.
        * If fixing bug in one module, requires changes in another module as well, then the system is not orthogonal.
* Reversability: 
    * In the ever-changing world, as much as we would like the requirements to be frozen, they change, and critical decisions aren’t easily reversible.
    * Sticking to DRY Principle and decoupling makes reversibility possible if not very easy since there are no final decisions.
    * Flexible Architecture:
        * Favor SOA and Micro-services.
        * Tracer Bullets: Tracer bullets are loaded at intervals on the ammo belt alongside regular ammunition, when they’re fired phosphorus in them ignites and leaves a pyrotechnic trail from gun to wherever they hit. Tracer bullets are preferred when firing a machine gun in dark to labor intensive target calculation because feed back is immediate and they operate in the same environment as the actual ammunition. Analogy although is violent applies to a new project, since a new project has a quite a bit of unknowns just like shooting in the dark, whether its’ unfamiliarity of end users’ to what you’re building, their requirements being vague, or your unfamiliarity towards the platform or algorithm being used. One can either handle these by laboriously documenting every requirement or use tracer bullets which pragmatic programmers prefer.  Code that glows in the dark: Tracer code is not disposable: you write it for keeps. It contains all the error checking, structuring, documentation and self-checking that any piece that production has. It is not simply fully functional, but it has achieved the end-to-end connection of components of the system, you can check how close the to the target you are and adjust as necessary. Trace development is consistent with the idea that the project is never finished: there will always be changes and required functions to add. It is an incremental approach. Tracer code has the below advantages,
            * Users get to see something working early: They contribute to the progress of the project increasing the buy-in.
            *  Developers build a structure to work in: Because it is built end-to-end there is consistency.
            * You have an integration platform: As system already has end-to-end connection, integration is seamless and the impact of the integration is more apparent, and testing is more accurate.
            * You will have something to demonstrate
            * You have a better feel for progress  Tracer Bullets don’t always hit their target: You use this technique when you’re not 100% certain of where you’re going. You need to work out what you need to change it to bring near target, and because this is a lean development methodology, and it is a small body of code change having low inertia - changes are easy and quick to make, and also every major component of the application is shown to the user, the users will be confident on what they’re saying is real and not just a specification on the paper.  Tracer code versus Prototyping: Prototyping involves, exploring specific aspects of the final system, and throwing away what was lashed out during trying out the concept and recode it properly using the lessons learnt. Tracer approach however addresses a different problem, you need to know how your application hangs as whole. You show the users of the application how it interacts while giving the developers the architectural skeleton on which they can further develop. The framework stays intact as you continue to develop and the applications continues to behave as it did before. Distinction is Prototyping generates disposable code where as the Tracer code is lean and complete, and forms the part of the skeleton of the final system.
* Prototypes and Post-it Notes: We build software prototypes to analyze and expose risk, and offer the chances of correction at greatly reduced cost. Prototypes usually target testing one or more specific aspects of the project. Prototypes need not always be code based, something as simple as Post-It notes explaining application flow, or poorly drawn diagram on whiteboard or paint representing an UI can be a prototype. Prototypes can ignore unimportant details, such as performance/results during UI mock up or UI during performance prototype. If the environments doesn’t allow you for ignoring such details, then perhaps it is a Tracer Bullet style development than prototyping.
    * Things to Prototype: Anything which carries risk, haven’t been tried before, is absolutely critical to the final system, unproven, experimental, double, or you’re not comfortable with can be prototyped. Prototyping is learning experience its value doesn’t lie in the code produced but the lessons learned.
    * How to use prototypes:
        * When building a prototype you can ignore correctness, completeness, robustness or style.
        * Since a prototype is supposed to gloss over details, it is safe to use a very high level language which will defer many details and focus on aspect being prototyped. 
    * Prototyping Architecture: As opposed to Tracer Bullets, although we are trying to discover who the system hangs while prototyping architecture, none of the individual models in the architecture needs to be functional. Below are the areas which one usually have to look at while prototyping architecture,
        * What are major components of the architecture? How will they collaborate? Are the decoupled enough?
        * What are the potential sources of duplication? Are Interface definitions and constraints acceptable? Does every model can access the data it needs, when it needs it?
    * Prototypes are always throw-away, no matter how attractive they are. Set this expectation right with the team. In case they are not in agreement, then TracerBullet Style development is more suited for your team than prototyping.
* Estimating: Check for the context before giving estimates, do they need a ballpark figure or they’re looking for accurate estimates.
    * How accurate is accurate enough
        * When your grandmother asks when you will arrive, she is wondering whether you will make it for lunch or dinner. On the other hand when diver trapped underwater and is running out of air, the estimates he is interested are down to the second. 
        * Value of Pi, would depend on what you’re doing with it, if you want to know how much edging to buy to put around circular bed, value of 3 should be good, if you are a high school student trying to solve a math problem, then 22/7 should be good, or if you are a NASA scientist, PI’s value to 12 decimal sometimes is not accurate enough.
        * Units used makes difference in interpretation, if your estimates suggests 130 days, people will expect you to deliver it pretty closely However if you say 6 months (although it is the same amount of time) they will know to look somewhere between 5-7 months. Below are some recommendations,
Duration	Quote estimate in
1–15 days	days
3–8 weeks	weeks
8–30 weeks	months
30+ weeks	think hard before giving an estimate
    * Where do estimates come from? All estimates are based on models of the problem. A basic estimating trick which usually gives good answers is ask someone who have already done it. 
        * Understand what is being asked: Consider Scope of the problem and Accuracy of the Estimation being demanded for before answering. Example “Assuming there are no traffic incidents and there’s gas in car I will be there in 20 mins.”
        * Build the Model of System: From your understanding of what is being asked build a rough bare-bones mental model. For example, to estimate the response times, you will consider server performance and the traffic rate as a parameters and give an estimate on the basis of those parameters. Model building can be very useful in long term, since it allows discovery of the underlying patterns and the process that were not apparent on the surface. “You asked for an estimate to do X, however a variant of X, Y can be delivered in half the time, which lacks in only one small feature.”
        * Break down the model into components: Decompose the mental model into smaller components and determine how each of these smaller components contribute to the end result.
        * Give each parameter a Value: On the basis of how the components contribute to the end result, provide estimates for these components by assigning them a value.
        * Calculate the Answers: Only simplest cases will have single answer. Complex Systems, having multiple components contributing to the end result of the system will have varying result depending on the variations introduced by the smaller components. Capture all these variations in a spread-sheet.
        * Keep track of your estimating prowess: Keep track of the hits and misses of your estimates. Analyze what caused a miss, was it because of incorrect mental model, or because of a missed parameter. Keeping it in mind will help you get better at subsequent estimtates.
        * Estimating Project Schedules: Normal rules of estimating can break down in the face of complexities and vagaries of sizable application development. Often the only way to determine the timetable of a project is by gaining experience on the same project. This is usually the case for iteratively developed projects. This might not be a popular answer with the management who typically want a single, hard-and-fast number before project even starts. You will have to help them understand that team, the productivity and environment will determine the schedule, and as a part of each iteration, the schedule will get more accurate.
    * What to say when asked for an estimate: You will always say “I’ll get back to you.” You will almost always get the accurate result if you slow down the process, spend time on going through the steps above described.
