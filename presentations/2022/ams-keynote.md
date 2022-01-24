---
title: AMS 2022 Keynote
separator: <!--s-->
verticalSeparator: <!--v-->
revealOptions:
  transition: 'fade'
---

## Building Tools for the Scientific Python Community

<hr>

<font size="7">_Anderson Banihirwe_, [@andersy005](https://github.com/andersy005)<img src="assets/assets/Github/GitHub-Mark-32px.png"></font>

<font size="4.5">Software Engineer @ The National Center for Atmospheric Research</font>

<font size="4.5">12th Symposium on Advances in Modeling and Analysis Using Python | AMS 2022 | 2022-01-19</font>

Note: test note

<!--s-->

![](assets/assets/misc/quiz-how-do-you-engage-with-foss.png)

<!--s-->

## Open Source Software

<hr>

The Foundational Layer of Earth System Analytics

<img src="assets/assets/misc/xkcd_dependency.png" alt="https://xkcd.com/2347/">(**xkcd2347**)

Note: Open source software powers much of the modern science even though its creators and maintainers are often not paid. It's easy to be a beneficiary of this ecosytem of tools without realizing it's there.

<!--s-->

## The Principles of Open Source Software

<hr>

- The availability of source code and the right to modify ("free as in speech") <!-- .element: class="fragment" data-fragment-index="1" -->
- The Open source software must be free to use ("free as in beer") <!-- .element: class="fragment" data-fragment-index="2" -->
- The ethos of volunter stewardship and commmunity pervades open source software <!-- .element: class="fragment" data-fragment-index="3" -->

Note: The source code must be open and available to anyone who wants to use it. You cannot charge people to use code that they are writing or have written. That means that you cannot simply take the code and charge money directly for it. Open source development could be looked at as a form of volunteering. Many developers have donated their time to either maintain or contribute to open source projects. These developers may not care about being compensated for their time—they are just happy for the experience, challenge or may just like helping others.

<!--v-->

## It's All About the People

<hr>

<img width="70%" src="assets/assets/misc/pangeo-sprint.jpeg" alt="Pangeo Sprints in Action">**Hanson2019**

Note: People build the software. People maintain the software. People form communities to support both the software and the people who use it.

<!--s-->

## The Few, Building for the Many

<hr>

<!--v-->

**GitHub Statistics as of January 23, 2022**

|            | Stars                                                                                                           | Forks                                                                                                      | Contributors                                                                                                             |
| ---------- | --------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------ |
| Xarray     | ![GitHub Repo stars](https://img.shields.io/github/stars/pydata/xarray?logo=github&style=for-the-badge)         | ![GitHub forks](https://img.shields.io/github/forks/pydata/xarray?logo=github&style=for-the-badge)         | ![GitHub contributors](https://img.shields.io/github/contributors/pydata/xarray?logo=github&style=for-the-badge)         |
| Dask       | ![GitHub Repo stars](https://img.shields.io/github/stars/dask/dask?logo=github&style=for-the-badge)             | ![GitHub forks](https://img.shields.io/github/forks/dask/dask?logo=github&style=for-the-badge)             | ![GitHub contributors](https://img.shields.io/github/contributors/dask/dask?logo=github&style=for-the-badge)             |
| Pandas     | ![GitHub Repo stars](https://img.shields.io/github/stars/pandas-dev/pandas?logo=github&style=for-the-badge)     | ![GitHub forks](https://img.shields.io/github/forks/pandas-dev/pandas?logo=github&style=for-the-badge)     | ![GitHub contributors](https://img.shields.io/github/contributors/pandas-dev/pandas?logo=github&style=for-the-badge)     |
| Matplotlib | ![GitHub Repo stars](https://img.shields.io/github/stars/matplotlib/matplotlib?logo=github&style=for-the-badge) | ![GitHub forks](https://img.shields.io/github/forks/matplotlib/matplotlib?logo=github&style=for-the-badge) | ![GitHub contributors](https://img.shields.io/github/contributors/matplotlib/matplotlib?logo=github&style=for-the-badge) |
| NumPy      | ![GitHub Repo stars](https://img.shields.io/github/stars/numpy/numpy?logo=github&style=for-the-badge)           | ![GitHub forks](https://img.shields.io/github/forks/numpy/numpy?logo=github&style=for-the-badge)           | ![GitHub contributors](https://img.shields.io/github/contributors/numpy/numpy?logo=github&style=for-the-badge)           |

Note: These numbers paint a picture of many more users than contributors for the most popular open source software in the Scintific Python stack. it’s really important to recognize that the github repository does not fully represent a project. There’s quite a lot of crucial, untracked work that goes on in the background such as:

<!--v-->

**A GitHub repository is only part of the story**

> <mark>many of the tasks involved in running a sustainable project don’t involve writing any code at all</mark>, behind every successful, sustainable open source project are many people making non-code contributions that are necessary to keep everything working. — [Andrew Nesbitt](https://nesbitt.io/2017/11/10/what-does-a-sustainable-open-source-project-look-like.html)

<!--v-->

<img width="65%" src="assets/assets/misc/open-source-background-activities.png" alt="Open Source background activities">(**Ram2019**)

<!--v-->

![](assets/assets/misc/quiz-untracked-work.png)

<!--s-->

## The Experience of Maintaining Open Source Software

<hr>

<!--v-->

#### The Experience of Maintaining Open Source Software

<hr>

#### The 👍🏽

- Open source maintainance looks good on a resume (**Malone2020**)
- Open source maintainance can provide the satisfaction of having an impact in the community (**Malone2020**)
- Open source software provides talent-recruiting opportunities for institutions (**Malone2020**)
<!--v-->

#### The Experience of Maintaining Open Source Software

<hr>

#### The 👎🏽

- Open source maintainers usually have 'day jobs'. So, open source work is usually done in their limited free time. (**Malone2020**)
- Burnout is common (**Malone2020**)
  - Often exacerbated by a subset of users who complain, often loudly about the perceived shortcomings of the software. (**Malone2020**)

<!--v-->

**Example: Walrus Operator Controversy**

> The straw that broke the camel's back was a very contentious Python enhancement proposal, where after I had accepted it, people went to social media like Twitter and said things that really hurt me personally. And some of the people who said hurtful things were actually core Python developers, so I felt that I didn't quite have the trust of the Python core developer team anymore. — Guido van Rossum

Note: The introduction of the walrus operator into Python 3.8 is one of the reasons why Guido van Rossum stepped down from his position as BDFL (Benevolent Dictator For Life). See Guido’s reply below to why he stepped down as BDFL.

<!--s-->

## Keeping the Python Scientific Ecosystem Healthy

<hr>

> Give a man a fish and you feed him for a day. Write a program to fish for him and you maintain it for a lifetime. — [Tim Hopper](https://www.nature.com/articles/d41586-019-02046-0) (**Nowogrodzki2019**)

Note: As many of us know too well, starting a new projects can generate more excitement than keeping the projecting running smoothly. But maintainance is a key part of the project and requires real investment. It's often not glamorous, and it's critical for the overall health of the ecosystem.

<!--v-->

### Keeping the Python Scientific Ecosystem Healthy

<hr>

#### Contributing back

- Give back to the Python Scientific Community <!-- .element: class="fragment" data-fragment-index="1" -->
- Can take many forms <!-- .element: class="fragment" data-fragment-index="2" -->
  - Service contributions (pull requests reviews, bug fixes, outreach, etc.) <!-- .element: class="fragment" data-fragment-index="3" -->
  - Psychological support and encouragement (e.g. thank maintainers when you get a chance) <!-- .element: class="fragment" data-fragment-index="4" -->
  - And, of course, monetary contributions (donations) when you can afford it. <!-- .element: class="fragment" data-fragment-index="5" -->
- Cite the open source software in your academic/research work <!-- .element: class="fragment" data-fragment-index="6" -->

Note: If a research lab uses open source software, the resulting papers should cite the software the same way as any other reference.

<!--v-->

### Keeping the Python Scientific Ecosystem Healthy

<hr>

#### Institutional Support (**Rocklin2019**)

- Develop learning materials to help users transition to the new open source software <!-- .element: class="fragment" data-fragment-index="1" -->
- Enable employees to spend time maintaining upstream projects and ensure that this time counts towards their career advancement <!-- .element: class="fragment" data-fragment-index="2" -->
- Contribute code upstream either to mainline packages or new subpackages <!-- .element: class="fragment" data-fragment-index="3" -->
- Co-write grant proposals with maintainers of the core project <!-- .element: class="fragment" data-fragment-index="4" -->

Note: (1) You can build teaching materials like blogposts, how-to guides, and online tutorials that assist the non-early-adopters to transition more smoothly. You can provide in-person teaching at conferences and meetings common to your community. It’s likely that the open source ecosystem that you’re transitioning to already has materials that you can copy-and-modify for your domain. (2) If you are a supervisor, You should explicitly give your time within the work schedule to continue these activities. The work that they do may not be explicitly within scope for your institution, but having them active within the core of a project makes sure that the mission of your institution will be well represented in the future of the open source project. Maintaining a widely cited software project should convey academic bona fides on par with writing a widely cited paper (4) If your institution provides or applies for external funding, consider writing up a grant proposal that has your institution and the OSS project collaborating for a few years. You focus on your domain and leave the OSS project maintainers to handle some of the gritty technical details that you anticipate will arise. Most of those details are hopefully things that are general purpose and that they wanted to fix anyway. It’s usually pretty easy to find a set of features that both parties would be very happy to see completed.

<!--s-->

## Conclusion

- Open source software is ultimately a feedback loop between maintainers and the community
- Giving back is necessary for a healthy ecosystem

Note: Open source is ultimately a feedback loop between maintainers and the community, where both learn from and give back to each other. Giving back takes many forms; recognition is really important. But prioritization is necessary for a healthy community. Taking care of your own needs as a maintainer is critically important.

<!--s-->

## Thank You!

<img width="50%" src="assets/assets/misc/working-in-public.png">

<!--s-->

## Attributions

<hr>

- **Ram2019**: [What it takes to sustain an open source project](https://inundata.org/talks/sdss/)
- **xkcd2347**: [Dependency](https://xkcd.com/2347/)
- **Hanson2019**: Pangeo Sprints in Action by [@ Matthew Hanson](https://www.linkedin.com/in/geoskeptic/)

<!--v-->

## Attributions

<hr>

- **Nowogrodzki2019**: Nowogrodzki, A. (2019). [How to support open-source software and stay sane. Nature, 571(7763), 133–134](https://doi.org/10.1038/d41586-019-02046-0). [10.1038/d41586-019-02046-0](https://doi.org/10.1038/d41586-019-02046-0)

- **Rocklin2019**: [Public Institutions and Open Source Software](http://matthewrocklin.com/blog/work/2018/08/21/institutional-open-source)

- **Malone2020**: Malone, K., & Wolski, R. (2020). [Doing Data Science on the Shoulders of Giants: The Value of Open Source Software for the Data Science Community](https://doi.org/10.1162/99608f92.268cc8e4). Harvard Data Science Review, 2(2). [10.1162/99608f92.268cc8e4](https://doi.org/10.1162/99608f92.268cc8e4)

Note: Open source software powers much of the modern world even though its creators and maintainers are not paid. And in fact, maintaining a popular open source package is quite expensive in terms of the attention and hours required of a skilled software developer who could spend their time elsewhere. So why do developers do it? This is the question addressed in Nadia Eghbal’s recent book, Working in Public: The Making and Maintenance of Open Source Software. Eghbal is a writer who has focused on this issue for the past 5 years, including several years at GitHub, the largest open source repository. She is well suited to tackle the question
