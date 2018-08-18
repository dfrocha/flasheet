# flasheet
*Real-time flash tool*

The goal of the project is to simplify the process of estimating and publishing
end-of-day P&L (profit and loss), CV (client value) or any other type of results.
The tool should behave as a trading tool allowing simple and fast user interactions.
Users should be able to define their own templates and save them for later.

**Requirements:**

1. Data inputs should be able to come from multiple sources
    * Direct data entry via UI editors
    * Pulled from other/external systems directly
    * Streaming from their own excel sheets


2. Templates should include:
    * List of books that are in-scope
    * How should they be grouped based on existing meta-data or entered values
    * Which measures should be published
    * What source of data should be used for each one of the rows


3. Data submissions shouldn't hold the user back
    * Every save/update should be delegated to parallel requests providing status updates
      * (push-in-progress)
      * (pushed-to-target system)
      * (push-fail: error message)
      * (pushed-with-warnings: warning message)


4. Bi-directional flow
    * Cells should be invalidated if the underlying data was saved by someone else
    while the current user had the same row/book open in the template. The user should
    be notified about the event and be allowed to decide to take in the update or reject it.
