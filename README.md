# ECE444-F2023-Lab5

### What are the pros and cons of TDD? 
Test-Driven Development (TDD) is an approach that prioritizes creating tests before writing the actual code. This approach entails writing a failing test and then developing the code to make that test pass. As with all software development approaches, TDD has its share of pros and cons. Regarding the pros, since tests are created at the start of the software development process, it allows developers to spend the time to produce high-quality tests. Consequently, the testing phase is not as rushed as it might be with other approaches that delay testing until the final stages. Furthermore, because tests are established before code implementation, any issues can be identified very early in the development process. TDD also necessitates the creation of tests for each piece of functionality. This encourages developers to write clean, high-quality, and maintainable code, resulting in improved code quality, fewer bugs, and more robust software. When collaborating within a team on a project, TDD proves especially beneficial for promoting early discussions about the expected behavior of the software. During the test creation process, all team members must align on how they want the software to respond to various scenarios, fostering better collaboration among the team. As for the cons of TDD, writing tests before developing the code can slow down the initial coding process. Writing tests as an initial step can lead to less software being writted earlier in the development cycle. Another con is that TDD follows a timeline that is different from many other approaches. It can be challenging for developers who are new to using TDD to learn to write effective tests prior to the development of the code. This is a learning curve that can be difficult and time consuming. TDD is also not an strategy that is suitable for all projects. It can work very well for projects with clear requirements and well-defined behaviour but it is not an effective approach for experimental projects where the functionality and behaviour of the outcome may change over time. Overall, the TDD approach has both advantages and disadvantages but is a strategy that is worth knowing and learning about.

### Test function written by me for group project: 
    def test_search_clubs_with_user_input(client, user_search_string):

        response = client.post('/club_search', data={'query': user_search_string})

        assert user_search_string.encode() in response.data

        response_data = json.loads(response.data)

        for club in response_data:
            assert user_search_string in club['name']
