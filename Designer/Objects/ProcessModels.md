# Process Models
- **Naming Convention:** `AO_intialProcess`
- **Process Model Palette 2 Views**
    - Analyst View
    - Designer View

- **Node and Smart Service Palette**

### Standard Nodes(3)
- has three sections, activities events and gateways
- **Activities:** used to capture or process business data
    - **Script Task:** when you need modify or manipulate the data after a form is submitted
    - **Sub Process:** when you need a second process to be triggered in some way from a main process
    - **User Input:** when something requires user intervention


### Events(6)
- controls workflow, enable designers to start stop or continue the progress of a workflow
1. **[Timer](https://docs.appian.com/suite/help/21.2/Intermediate_Event_-_Timer.html):**
        - can either be added to the process flow by themselves, or they can be added within an Appian Smart Service to trigger an Exception Flow or an Escalation
2:3. **[Send Message](https://docs.appian.com/suite/help/21.2/Send_Message_Event.html) and [Recevie Message](https://docs.appian.com/suite/help/21.2/Receive_Message_Event.html)**
        - a Send Message event can be used to generate a message that is made available to all Receive Message events (which are actively listening for messages). Messages sent to events that are not active (either paused, yet to be activated, passed in the process flow, or in an unpublished process model) are discarded.
4. **[Rule](https://docs.appian.com/suite/help/21.2/Rule_Event.html):** when there are certain conditions that need to be met before the process flow proceeds, remains active until the rule evaluates to true
        -  an either be added to the process flow as a process node, or they can be used within an activity to trigger an exception flow
5. **[End](https://docs.appian.com/suite/help/21.2/End_Event.html):** needs at least one but can have multiple
        - with multiple end events the different branches of a process remain active until each active path reaches one of the multiple End Event nodes
        - Can add a Send Message or/and Terminate Process Triggers
        - **Send Message Trigger:** used to pass information from one process to another
            - **NOT USED TO NOTIFY USERS**
        - **Terminate:** used to stop all branches of a process with multiple end events
            - since a process can have multiple end events, a Terminate Process even can be used to stop all branches of a process, even if one or more branches have not yet reached an End Event node
                    - From the end node's properties click the `Results` tab then select `Terminate Process`, denoted by a solid circle inside the end node icon
6. **Start:** each process needs to have only one


- **Gateways:** used to control the workflow based on business logic(XOR(`X`), OR(`O`), AND(`+`), COMPLEX`*`)
- **Smart Services:** provide specilized business services, complete specific tasks(sending an email, creating a folder or calling an integration)
    - **Appian Smart Services:** deal with appian objects(documents, users, or constants)
    - **Integration Services:** deal with data

[More...](https://docs.appian.com/suite/help/21.2/process-model-object.html)