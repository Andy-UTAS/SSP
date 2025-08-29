# Course information

## Administration

The solid-state component of the course will run for seven weeks, beginning in week 7 and concluding at the end of semester. In years gone by, the solid-state physics and semiconductor physics components of the course were explicitly differentiated; however, in my teaching of the course, the two will be more closely intertwined, with semiconductors being considered a flourish to the foundational content that we shall construct during our adventures describing matter.

!!! Danger "Prerequisite knowledge"

    The content covered in this course is complicated, and without the frim bedrock of requisite knowledge and associated competencies, attempts to construct additional structures may be compromised. It is critical that one is comfortable with the following:

    - The principles and machinery of quantum mechanics. Explicitly, an understanding of how physical systems and their evolution are modelled using the Schrödinger equation, along with a fluency in common examples (e.g. particle in a box, harmonic oscillator, the hydrogen atom), and a vague familiarity with Dirac notation is assumed.
    - Thermodynamic quantities and concepts abound, with statistical mechanics looming large in the background. Conveniently, you have just completed a course in statistical mechanics, but it will be assumed that you are comfortable with the content

    <u>It is my intention that</u> you will be required to call upon many of the other tools from the toolbox that you have been developing during your studies, with the explicit aim of further honing these tools, and maybe adding a few to the kit.

### Delivery of content

The course will operate in a largely conventional configuration: workshops will be held three times per week, with a tutorial taking place at the end of the week. Workshops are designed to be interactive, and will include problem solving and coding examples, whereas tutorials will exclusively be used for discussions and problem solving. An important running note is that problems for tutorials will be released at the start of the week, and each class member will be assigned a problem, which can be tackled individually or with your classmates; however, those assigned to each problem will be required to present their solution of the problem to the rest of the class. **It is important to note** that solutions to tutorial problems will not be immediately distributed: as a class you will be preparing these for one another through your work, so it is important to participate and contribute to this process.

### Subject matter

The content for this course draws heavily from off the excellent text [The Oxford Solid State Basics](https://global.oup.com/academic/product/the-oxford-solid-state-basics-9780199680771?cc=au&lang=en&) by [Steven H. Simon](https://www-thphys.physics.ox.ac.uk/people/SteveSimon/); indeed, the book is the prescribed text for the course. This means that it is assumed that you will access to this book. This particular text was chosen because of its concise discussion of the content, its accessibility, and the wry whit which permeates the content, in concert with the availability of [freely distributed pre-print of the book](http://www-thphys.physics.ox.ac.uk/people/SteveSimon/condmat2012/LectureNotes2012.pdf). I will be working from the printed text, and I encourage you to do the same.

!!! warning "Unsupported material"

    Steven himself has said that the preprint is roughly 85% of the book; however, if you elect to work from the preprint, you do so at your own risk.

### Course outline

!!! summary "Course summary"

    This subject is designed to serve as _an introduction_ into the field of solid-state physics. Solid-state physics is the largest field of condensed matter physics, which itself is the largest branch of physics, and so there is only so much material we will cover. The trajectory we shall take begins with _bulk_ descriptors of solids, into considering the fundamental nature of solids, collective behaviour within solids, and the place of these systems in the real world.

A rough outline of the course is as follows:

  1. An introduction to solid-state physics
  2. The structure of materials
  3. Solids in one dimension
  4. The geometry of solids
  5. Electrons in solids
  6. Applications
  7. Magnetism

with approximately one week devoted to each topic, but with the natural ebb and flow ultimately dictating the timeline.

### The notes

The notes are designed to be consumed in concert to the workshops, with certain aspects highlighted differently in the different media, and in extreme cases with different paths used to arrive at the same destination. One of my aims is to expose you to different ways of thinking about problems, not just have the same method and then just "press play".

#### Structure of sections

!!! danger  "Expected competencies"

    Content has been constructed with the assumption that the material is consumed sequentially, with sections often explicitly relying on results from previous work. I have also to placed _expected competency_ markers at the beginning of each section, outlining knowledge that I expect you to have seen in other areas of study, and importantly, **these are cumulative** from section to section.

!!! note  "Text reference"

    You will also encounter _text references_ at the beginning of each section, relating to the relevant content in the course text [The Oxford Solid State Basics](https://global.oup.com/academic/product/the-oxford-solid-state-basics-9780199680771?cc=au&lang=en&).

!!! info "Computational content"

    Computational content, which is normally just the jupyter notebook associated with the section, also appears at the top of the page, but may also contain links to other software or pertinent computational material.

### The content

Course content is available only to those enrolled at the University of Tasmania, and is best accessed through the course [MyLO page](https://mylo.utas.edu.au/d2l/home/729400).

---

## Support

<figure>
  <img src="../images/zelda.png">
  <figcaption> You are not on this journey alone: there are many avenues available to you to help you on the journey (depending on your inclination to play antiquated video games, you may recognise this as a scene from <a href="https://en.wikipedia.org/wiki/The_Legend_of_Zelda">The Legend of Zelda</a>).</figcaption>
</figure>

### "_We are all in this together_" :fontawesome-solid-virus-covid:{ title="Can you tell that I developed this site during the COVID-19 pandemic? " }

Your progress through the course is necessarily subjective and thus an individual experience, but the you needn't undertake the journey alone. Indeed, I strongly encourage collaboration and the structure of workshop and tutorial sessions is deliberately geared towards discussion, the exchange of ideas, and collective problem solving more so than the execution of a solution finding program.

To mediate collective input, there are a plethora of community-based platforms, all of which I will contribute to with the goal of enhancing and facilitating your learning experience. These are listed below in order of utility:

  - [:fontawesome-brands-discourse:](https://discourse.utasphys.cloud.edu.au/c/ssp/9): [Discourse](https://www.discourse.org/) is a discussion platform (think [StackExchange](https://stackexchange.com/)) but specifically for physics at UTAS. The prime reason for using this service is that questions remain within class topics, meaning that students that take this class in the future can also look over our discussions :material-test-tube:{ title="This is a test feature, but hopefully it catches on" }
  - [:fontawesome-brands-discord:](https://discord.gg/ZDP4S4c6): [Discord](https://discord.com/) is a synchronous communication platform (messaging service) which can be great for immediate communication and discussion between a community.
  - [:material-forum-outline:](https://mylo.utas.edu.au/d2l/le/729400/discussions/List): The KYA322 discussion board on MyLO can be used for all manner of discussion and is the supported message platform of UTAS. It is no coincidence that I recommend it below the other platforms.


### Computational resources

[<i class="fab fa-python fa-5x"></i>](https://jove2021.cloud.edu.au/){ .md-button .md-button--primary class="text-center" style="margin-left: 45%"}

As part of the course, it will be expected that you perform calculations and computations. You are welcome to do this in which ever language you prefer, but it is __strongly__ recommended that you use `Python`, and indeed, this is the only language that will be formally supported. In order to ensure equitable and easy access to Python computing resources, a [Jupyter Notebook](https://jupyter.org/) server has been established, which allows for one to write and execute code via a web browser. The server is named Jove[^1], and access is through the [JupyterHub portal](https://jove2021.cloud.edu.au/). You will need to create an account to start using the server, but beyond this is should be click and go. Should you experience any issues using the platform, please refer to the notes on computation as hosted on [POLUS](https://polus.utasphys.cloud.edu.au/reference/computation/#cloud-usage) and if you have issues accessing the server (e.g. a 404 error) please [contact me](mailto:andrew.mcculloch@utas.edu.au) directly and describe the problem.

Should you have a machine upon which you already have, or you wish to deploy, your own instance of `Python`, this is perfectly acceptable, but note that you will have to manually import the distributed materials into Jupyter. This can be effectively accomplished using the [clone functionality of GitHub](https://docs.github.com/en/github/creating-cloning-and-archiving-repositories/cloning-a-repository-from-github/cloning-a-repository) as this is where the [course content](https://github.com/Andy-UTAS/Solid-state) is hosted.

[^1]: For those wondering, [Jove is an alternate name](https://en.wikipedia.org/wiki/Jupiter_(mythology)) for the Roman god Jupiter.

---

!!! bug "Gotta catch 'em all"
    This site was developed and is maintained and hosted solely by [me](https://discover.utas.edu.au/andrew.mcculloch). If you come across mistakes, bugs, or have ideas for content or any other quality-of-life improvements, [please get in contact](mailto:andrew.mcculloch@utas.edu.au)!

--8<-- "includes/abbreviations.md"
