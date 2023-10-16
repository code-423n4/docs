# Preparing for a Code4rena audit

These four things will help you get the most value from your Code4rena audit:

1. **Prepare a self-contained repository,** with working commands that will build (at least) all in-scope contracts, and commands that will run tests producing gas reports for the relevant contracts
2. **Organized repo & `README`,** including well-commented code
3. **Share a video walkthrough,** if possible (you can link this from the repo and also pop it into your warden-facing channel in our Discord)
4. **Your presence in the C4 Discord** - easy access for warden questions during your audit

## Example repos

Want some examples of a well-organized repo? Here are a couple that are worth looking at as you set up your repo - particularly with regard to the context-setting in the `README`: 

- [Ajna Protocol](https://github.com/code-423n4/2023-05-ajna)
- [Maia DAO Ecosystem](https://github.com/code-423n4/2023-05-maia)

## Technical notes for engineers

To increase the chances of wardens finding all bugs in your code, there are a few technical things your team can do to contribute to the quality of the audit:

- **Clean code**
    The easier your code is to understand, the more time and energy wardens can dedicate to finding bugs. 
    - Using explanatory function and variable names
    - Using enums when relevant, rather than plain numbers
- **Docs, ideally covering 3 levels:**
    - High-level explanation of the aims, features and functionality of the project (less technical aspect, and more user end aspect)
    - High level overview of the system design: some projects include a flowchart; feel free to add it if it seems to fit
    - Code comments: explain any nontrivial part of the code
        - Most functions
        - Any complex design or nontrivial design choice in the code
        - Anything in the code that might make an external reviewer scratch their head.
- **Marking known issues:** It's important that our wardens don't waste their time on known issues and focus their time and energy on finding relevant bugs; therefore it's important that you let us know if there are any known issues in the code, whether you intend in mitigating them or not.
- **Incomplete code:** Our wardens will work under the assumption that this is the final form of the code that's going to be deployed to the blockchain. If you plan on any modification of the code before deployment (except for mitigation of C4's findings), please note this clearly in your `README` file, so that the wardens will have the correct assumptions about the code.
- **Tests:**
    - Some bugs can easily be found by simple tests; therefore it's better to cover as much as possible with tests so that the wardens don't need to spend time on finding and reporting them and can focus on finding the more complicated bugs
    - We don't expect you to rewrite your tests, but just in case you haven't written them yet, C4 wardens prefer `forge`, as it's easier to write and debug.
    - If you want to boost your test coverage, [Code4rena wardens can help with that.](https://medium.com/code4rena/new-to-code4rena-test-coverage-c548645404f9)
    - Whenever possible, please ensure that
        - test line coverage is high, since wardens often will modify existing tests in order to provide POCs, and need similar test cases to modify
        - build/test commands are complete and that they can be run in order, without modification, to get all of the tests passing
        - all tests pass, or reasons for failures passing are clearly explained
        - `slither .` from the project root works without error, or that expected errors are documented in this `README.md`
        - commands for running the tests include the appropriate arguments for showing gas reports
        - if the project is using foundry, that a complete `remappings.txt` is provided, so that tools such as VS Code that do not read `foundry.toml` can work properly
        - any failing commands or errors during the running of the build/tests/slither are documented, with the specific error message expected
