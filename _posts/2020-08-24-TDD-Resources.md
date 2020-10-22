## General

A misc. collection of interesting TDD resources.
- [Recap of major TDD principles](https://integralpath.blogs.com/thinkingoutloud/2005/09/principles_of_t.html)
- [How to think about refactoring as a key step in TDD](https://www.planetgeek.ch/2011/08/23/refactoring-in-test-driven-development/)  
- [A nice JS TDD setup](https://medium.com/p/55f59358253f)
- [Mocking is a code smell](https://medium.com/javascript-scene/mocking-is-a-code-smell-944a70c90a6a) -
  The author suggests that the need for mocking suggests excessively tight coupling.
- [James Shore on TDD Architecture that avoids mocks](https://www.jamesshore.com/v2/blog/2018/testing-without-mocks)
- Reducing the scope of possible errors is the key to developing quickly. If you have total confidence that your software worked five minutes ago, then only the actions you've taken in the last five minutes could cause it to fail now. 

## React

- [Kent Dodds' Common Mistakes With React Testing Library](https://kentcdodds.com/blog/common-mistakes-with-react-testing-library).  Note that by itself,
  Testing Library is (perhaps) not broad enough for TDD.  We need to augment it with enzyme or something.
- [Five Things You (Probably) Didn't Know About Testing Library](https://www.polvara.me/posts/five-things-you-didnt-know-about-testing-library/) -
  This article includes a bit about how to test a front-end table with Testing Library.
