# Coevolution framework

## MetaEdit
Git repository demonstrating 12 different scenarios on how MetaEdit+ supports co-evolution of domain-specific modeling languages, tools and models. Each scenario is its own version in Git, following on from the changes in the previous scenarios.

### Getting Started

1. Install MetaEdit+. 
MetaEdit+ user guide is available at https://metacase.com/support/55/manuals/ and integration with version control systems (VCS) is detailed in https://metacase.com/support/55/manuals/meplus/Mp-3_5.html. 

2. Fork the https://github.com/mccjpt/Gothic repository into your own VCS online. For simplicity, we'll assume your online VCS platform is GitHub and user name there is GITUSER.

3. Create a directory and settings for Git integration. For simplicity, we'll assume your local OS is Windows and user name is OSUSER.
   - In your MetaEdit+ working directory (by default C:\Users\OSUSER\Documents\MetaEdit+ 5.5), `mkdir git`. 
   - Add this new directory and _your_ GitHub account URL (without /Gothic suffix) to a `.vcsPaths` file in your MetaEdit+ working directory:

        ```
        gitBaseDir=C:\Users\OSUSER\Documents\MetaEdit+ 5.5\git
        gitBaseURL=https://github.com/GITUSER
        ```
4. Make a local clone of your fork. Run the following in a command prompt in your MetaEdit+ working directory, adjusting the location of the MetaEdit+ executable as necessary:

    ```
    set metaedit="C:\Program Files (x86)\MetaEdit+ 5.5\mep55.exe" fileInPatches
    %metaedit% textForMERL: "_vcsInitClone('Gothic')" logoutAndExit
    git config -f git\Gothic\.git\config --unset core.sharedRepository
    ```

    You'll be prompted for your GitHub password, and assuming all goes well you can close the command prompt at the end. (The last line is just to avoid a [bug](https://github.com/git-for-windows/git/issues/3110) in Git for Windows.)

4. Start MetaEdit+, select the 'Gothic' repository and 'Gothic Security' project, and Login. 
You can now seen the current version where all 12 scenarios been implemented. 

### Inspecting co-evolution scenarios individually
To see or conduct any particular scenario, checkout the version from your Git
1. Choose **Repository | Changes & Versions** and then checkout the desired version by selecting **Extra VCS Commands | CheckOut**. 
2. Enter the name for the new MetaEdit+ repository to be created (e.g. the name of the scenario, like GothicAfter4). 
3. Enter the Git hash for the desired version (version 0's hash to start from the beginning, version 1's hash for after scenario 1 etc.).
   - MetaEdit+ starts and opens the repository asking for login password (by default 'user'). Open the project to try out the desired co-evolution scenario.

_You can ignore Git's "detached head" warning: your local Git has already moved back to the latest version, matching your separate original Gothic MetaEdit+ repository._

### Prerequisites
MetaEdit+ 5.5 SR1, https://metacase.com/download



## Sirius/EMF

This README documents the series of commits made to the MetaModel Evolution Project repository. Each commit corresponds to specific evolution scenarios that have been applied to the metamodel. These scenarios include adding new concepts, modifying existing ones, and removing outdated elements. The changes aim to evolve the metamodel to adapt to new requirements and improve its functionality and usability.

### Commit List
- [Commit S0](https://github.com/MDEGroup/coevolution-impact-analysis/tree/7fffa200efbf1fe68012a25270176b2de2e4768a) - This commit stores the original implementation of the StateMachine modeling tools.
- [Commit S1](https://github.com/MDEGroup/coevolution-impact-analysis/tree/31a0f61511f404b81f1d6ad7b7cf15c4aaee489c) - Add Concept to Metamodel: Added a new Reset element to the State machine metamodel. This Reset has a set of events that trigger it.
- [Commit S2](https://github.com/MDEGroup/coevolution-impact-analysis/tree/b9f9d424151add89df09cb1ad67ebe39bfdbd732) - Add Constraint: Imposed a constraint where only one Reset can be defined in a State machine, and it can have only one Transition to a State there.
- [Commit S3](https://github.com/MDEGroup/coevolution-impact-analysis/tree/69f4ae3cd8b5fd80b0c7545f22432acf9ff60269) - Add Notation: Introduced a symbol for Reset and associated it with the Reset element.
- [Commit S4-S6](https://github.com/MDEGroup/coevolution-impact-analysis/tree/3728b6e924f57c16d8971f31d02f01327495e465) - Rename Concepts: Renamed the 'State' element in the metamodel to 'Situation.' No changes were made as constraints do not have names. Renamed the sub-symbol used in the Situation’s symbol.
- [Commit S7-S9](https://github.com/MDEGroup/coevolution-impact-analysis/tree/199eeeda9956374b475fc5b4cf04d0a26add99e0) - Remove Element from Metamodel: Removed the Reset element from the State machine. Eliminated the constraint allowing Reset to have a Transition to Situation. Removed the symbol associated with Reset.
- [Commit S10](https://github.com/MDEGroup/coevolution-impact-analysis/tree/5ac4d0999557d6eb94098badb4fe5684fb98d685) - Change Metamodel: Modified the Transition's Trigger to be specified at the Source end of the relationship.
- [Commit S11](https://github.com/MDEGroup/coevolution-impact-analysis/tree/bff1c9142a5be5215b5ff7caedb60c3933c474a2) - Change Constraint: Added Start, updated old Reset constraints to apply to Start, and allowed Start to be the Source of a Transition to a Situation.
- [Commit S12](https://github.com/MDEGroup/coevolution-impact-analysis/tree/f115b9189ebc0a23b692e06df2a64ae55518c24a) - Change Notation: Updated the Situation symbol to refer to a different subsymbol.

