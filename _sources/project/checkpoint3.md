<style>
/* DRAFT watermark with criss-cross pattern */
.draft-watermark {
  position: relative;
}

.draft-watermark::before,
.draft-watermark::after {
  content: "";
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 10000;
  background-image: 
    repeating-linear-gradient(45deg, 
      rgba(255, 0, 0, 0.07) 0px, 
      rgba(255, 0, 0, 0.07) 2px, 
      transparent 2px, 
      transparent 150px
    ),
    repeating-linear-gradient(-45deg, 
      rgba(255, 0, 0, 0.07) 0px, 
      rgba(255, 0, 0, 0.07) 2px, 
      transparent 2px, 
      transparent 150px
    );
  background-size: 250px 250px, 250px 250px;
  background-position: 0 0, 0 0;
}

.draft-watermark::before {
  content: "";
  background-image: 
    repeating-linear-gradient(45deg, 
      transparent 0px, 
      transparent 75px, 
      rgba(255, 0, 0, 0) 75px, 
      rgba(255, 0, 0, 0) 76px
    ),
    repeating-linear-gradient(-45deg, 
      transparent 0px, 
      transparent 75px, 
      rgba(255, 0, 0, 0) 75px, 
      rgba(255, 0, 0, 0) 76px
    );
}

/* Add DRAFT text at intersection points */
.draft-watermark::after {
  background: none;
  background-image: 
    repeating-linear-gradient(45deg, 
      transparent 0px, 
      transparent 125px, 
      rgba(255, 0, 0, 0.1) 125px, 
      rgba(255, 0, 0, 0.1) 126px
    ),
    repeating-linear-gradient(-45deg, 
      transparent 0px, 
      transparent 125px, 
      rgba(255, 0, 0, 0.1) 125px, 
      rgba(255, 0, 0, 0.1) 126px
    );
}

body {
  position: relative;
}

body::after {
  content: '';
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  pointer-events: none;
  z-index: 10000;
  background-image: 
    repeating-linear-gradient(45deg, 
      transparent, 
      transparent 120px, 
      rgba(255, 0, 0, 0) 120px, 
      rgba(255, 0, 0, 0) 250px
    ),
    repeating-linear-gradient(-45deg, 
      transparent, 
      transparent 120px, 
      rgba(255, 0, 0, 0) 120px, 
      rgba(255, 0, 0, 0) 250px
    );
}

.draft-text {
  position: fixed;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  pointer-events: none;
  z-index: 10001;
}

.draft-text::after {
  content: "";
  position: absolute;
  top: 0;
  left: 0;
  width: 100%;
  height: 100%;
  background-image: 
    repeating-linear-gradient(45deg, 
      transparent, 
      transparent 123px, 
      rgba(255, 0, 0, 0.1) 123px, 
      rgba(255, 0, 0, 0.1) 124px
    ),
    repeating-linear-gradient(-45deg, 
      transparent, 
      transparent 123px, 
      rgba(255, 0, 0, 0.1) 123px, 
      rgba(255, 0, 0, 0.1) 124px
    );
}

/* Add actual DRAFT text at intersection points */
.draft-text span {
  position: absolute;
  color: rgba(255, 0, 0, 0.1);
  font-weight: bold;
  font-family: sans-serif;
  font-size: 20px;
  transform: rotate(-45deg);
  white-space: nowrap;
}

/* Ensure watermark appears in print as well */
@media print {
  .draft-watermark::before,
  .draft-watermark::after,
  .draft-text,
  .draft-text::after,
  .draft-text span {
    position: fixed;
  }
}
</style>

<script>
document.addEventListener('DOMContentLoaded', function() {
  document.body.classList.add('draft-watermark');
  
  // Create a div for DRAFT text elements
  var draftTextDiv = document.createElement('div');
  draftTextDiv.className = 'draft-text';
  document.body.appendChild(draftTextDiv);
  
  // Create a grid of DRAFT texts
  var windowWidth = window.innerWidth;
  var windowHeight = window.innerHeight;
  
  // Place DRAFT text at grid intervals
  for (var y = 0; y < windowHeight; y += 250) {
    for (var x = 0; x < windowWidth; x += 250) {
      var draftSpan = document.createElement('span');
      draftSpan.textContent = 'DRAFT';
      draftSpan.style.left = x + 'px';
      draftSpan.style.top = y + 'px';
      draftTextDiv.appendChild(draftSpan);
    }
  }
});
</script>

# Checkpoint 3: Project Contribution & Reflection

**(40% of Project Grade)**

You've selected a robust open-source project and analyzed its development lifecycle. Now, it's time to put your understanding into practice and contribute to the project directly.

This final checkpoint is focused on **active participation** in your chosen open-source project. You will be forking the project repository, identifying and addressing real issues, implementing your solution, and submitting a pull request to contribute your changes back to the project. This experience will provide invaluable hands-on learning about collaborative software development in an open-source environment and solidify your understanding of software engineering principles in a practical context.

## Project Contribution Phase

While the following outlines a standard open source contribution workflow, **it's important to note that each project may have its own specific processes and guidelines**. As a good contributor, you should carefully read and follow your chosen project's contribution documentation, even when it deviates from these standard practices. Document any project-specific processes you encounter as part of your submission.

This phase typically involves the following key steps:

1. **Fork the Repository:** Create your own fork of the main project repository on GitHub. This will be your personal workspace to develop your contributions.

2. **Issue Identification and Selection:**
   * **Explore the Issue Tracker:** Navigate to the "Issues" section of your chosen project's GitHub repository.
   * **Identify "Good First Issues" or "Help Wanted" Issues:** Look for issues tagged as "good first issue," "help wanted," or similar labels. These are often issues that are well-defined and suitable for new contributors.
   * **Understand Issue Scope:** Carefully read the issue descriptions to understand the problem, the expected solution, and any relevant context. Consider the complexity and scope of the issue in relation to the remaining time in the project (4-5 weeks).
   * **Communicate and Claim an Issue:** Comment on the issue to express your interest in working on it and ask any clarifying questions to the project maintainers. This shows initiative and helps avoid duplicated effort. Some projects have a specific process for "claiming" issues to prevent conflicts.

3. **Development and Implementation:**
   * **Set up your Development Environment:** Follow the project's documentation to set up your local development environment. This usually involves cloning your forked repository, installing necessary dependencies, and configuring your tools.
   * **Create a Branch:** Create a new branch in your forked repository for your issue. This isolates your changes and keeps your main branch clean. Use a descriptive branch name related to the issue you are addressing (e.g., `fix-typo-in-docs`, `implement-feature-x`).
   * **Implement the Solution:** Write code, modify documentation, or perform other necessary tasks to address the issue you selected. Adhere to the project's coding standards, style guides, and any contribution guidelines you identified in Checkpoint 2.
   * **Test Your Changes:** Thoroughly test your solution to ensure it correctly addresses the issue and doesn't introduce new problems. Run existing tests and write new tests if necessary, as per the project's testing practices.

4. **Pull Request Submission:**
   * **Commit Your Changes:** Commit your changes to your branch with clear and descriptive commit messages. Follow the project's commit message conventions if specified.
   * **Push to Your Fork:** Push your branch to your forked repository on GitHub.
   * **Create a Pull Request (PR):** Navigate to your forked repository on GitHub and create a new pull request. The PR should target the main project's base branch (usually `main` or `develop`).
   * **Write a Clear PR Description:** In your PR description, clearly explain:
     * What issue your PR addresses (link to the issue).
     * What changes you have made and why.
     * Any relevant details about your implementation or testing.
     * Reference any discussions or communication you had with maintainers.
   * **Review and Respond to Feedback:** Project maintainers will review your pull request. Be prepared to respond to their feedback, answer questions, and make revisions to your code as requested. This is a crucial part of the open-source contribution process. Be patient and respectful during the review process.

5. **Iteration and Merge:**
   * **Address Feedback:** Revise your code based on the feedback from maintainers. Update your branch and push the changes to your fork; the pull request will automatically update.
   * **Merge (Potentially):** If your pull request is accepted and approved by the maintainers, it will be merged into the main project repository! Even if your PR is not merged within the timeframe of this checkpoint, the experience of contributing and receiving feedback is valuable and will be fully credited in your assessment.

## Deliverables

For this final checkpoint, you will submit a comprehensive document (PDF or Markdown) that includes the following:

1. **Contribution Summary (2-3 paragraphs):**
   * **Pull Request Link:** Provide a direct link to the pull request you submitted to the project's main repository.
   * **Issue Link:** Provide a direct link to the issue your contribution addresses.
   * **Contribution Description:** Briefly explain the specific contribution you made (e.g., bug fix, new feature, documentation improvement).
   * **Rationale:** Explain why you selected this particular issue to address (e.g., impact, learning opportunity, alignment with your skills).

2. **Project-Specific Contribution Process (1-2 paragraphs):**
   * **Documentation Review:** Describe the project's contribution guidelines and how they may differ from standard practices.
   * **Project-Specific Requirements:** Detail any unique processes, tools, or conventions required by the project (e.g., specific code formatters, testing frameworks, commit message formats).
   * **Communication Channels:** Identify the preferred communication channels used by the project (e.g., Discord, mailing lists, GitHub Discussions).

3. **Development Process Analysis (2-3 paragraphs):**
   * **Technical Approach:** Describe the approach you took to solve the issue, including:
     * Key technical decisions made during implementation
     * Tools and technologies you used
     * How you tested your solution
   * **Challenges Encountered:** Discuss any significant challenges you faced during development and how you overcame them.
   * **Community Interactions:** Summarize any communication you had with project maintainers or community members.

4. **SDLC in Practice (2-3 paragraphs):**
   * **SDLC Alignment:** Reflect on how your practical contribution experience aligned with the SDLC model you inferred in Checkpoint 2.
   * **Observable Practices:** Discuss which specific SDLC practices you observed in action during your contribution (e.g., code reviews, testing requirements, release management).
   * **Impact Analysis:** Analyze how the project's SDLC affected your contribution experience, both positively and negatively.

5. **Learning and Skills Development (1-2 paragraphs):**
   * **Technical Skills:** Identify specific technical skills you gained or improved through this contribution.
   * **Collaboration Skills:** Discuss what you learned about collaborative software engineering in an open-source context.
   * **Process Knowledge:** Reflect on your improved understanding of software development workflows.

6. **Future Contributions (1 paragraph):**
   * **Next Steps:** Identify potential future contributions you could make to this project.
   * **Growth Areas:** Highlight areas where you could further develop your skills to become a more effective contributor.
   * **Open Source Engagement:** Discuss how this experience has shaped your perspective on contributing to open-source projects in the future.


## Important Notes:

* **Project-Specific Guidelines:** Each open-source project has its own unique contribution workflow and guidelines. Your ability to adapt to and follow these project-specific requirements is a key part of this assessment.

* **Focus on the Process:** The primary goal of this checkpoint is the *process* of contributing to open source, not necessarily whether your pull request gets merged within the project timeframe. Effort, engagement, and learning are key to your assessment.

* **Communication is Key:** Don't hesitate to ask questions and engage with the project community. Open-source projects thrive on collaboration, and most maintainers are happy to assist new contributors.

* **Start Early:** Open-source contribution takes time, especially with code reviews and feedback cycles. Start exploring issues and working on your contribution immediately to allow sufficient time for the review process.

* **Document as You Go:** Keep notes throughout your contribution process - including screenshots of interesting interactions, links to relevant discussions, and reflections on challenges and solutions. These will be invaluable when preparing your final submission.

* **Be Persistent:** If your first issue attempt proves too challenging or gets claimed by someone else, don't be discouraged. Finding the right issue may take several attempts, especially in popular projects.

* **Quality Over Quantity:** A small, well-crafted contribution that demonstrates understanding of software engineering principles is more valuable than a large but poorly implemented one.

## Grading Rubric

| Criteria | Excellent (Points Range) | Good (Point Range) | Fair (Point Range) | Needs Improvement (Point Range) |
|:---------|:-------------------------|:-------------------|:-------------------|:-------------------------------|
| **1. Pull Request Submission & Meaningful Contribution (35 points)** | **31-35 pts:** PR submitted to main repository. Contribution is meaningful, addresses a real issue, and demonstrates effort and understanding of the project. Code/documentation follows project conventions perfectly. | **26-30 pts:** PR submitted. Contribution is relevant and shows effort, but might be less impactful. Code/documentation generally follows project conventions. | **21-25 pts:** PR submitted, but contribution is minor or shows some misunderstanding of project conventions. Some issues with code quality or documentation. | **0-20 pts:** PR not submitted or contribution is not a genuine attempt to address a project issue. Significant issues with code quality or documentation. |
| **2. Development Process Summary (20 points)** | **18-20 pts:** Comprehensive and well-articulated summary of the development process, highlighting challenges, solutions, and tools used. Demonstrates clear reflection and specific technical details. | **15-17 pts:** Good summary that describes the process and challenges, but could be more detailed or reflective. Some specific examples provided. | **12-14 pts:** Basic summary that outlines the process but lacks depth, specific technical details, or reflection on challenges and solutions. | **0-11 pts:** Summary is missing or very superficial and uninformative. Few or no specific technical details provided. |
| **3. Reflection on SDLC in Practice (20 points)** | **18-20 pts:** Insightful and well-reasoned reflection on the SDLC in practice, effectively linking practical experience to the SDLC analysis from Checkpoint 2. Identifies multiple specific SDLC practices observed. | **15-17 pts:** Good reflection that connects experience to SDLC, but could be more insightful or detailed. Identifies several SDLC practices with adequate analysis. | **12-14 pts:** Basic reflection with limited connections to SDLC analysis. Few SDLC practices identified with minimal analysis. | **0-11 pts:** Reflection is missing or shows no understanding of SDLC in practice. Fails to make connections between experience and theory. |
| **4. Learning and Future Contributions (15 points)** | **13-15 pts:** Clear and insightful summary of learning outcomes and future contribution potential. Articulates specific technical and collaborative skills gained. Shows genuine reflection on personal growth. | **10-12 pts:** Good summary of learning outcomes with some specific skills identified. Shows awareness of personal growth and potential future contributions. | **7-9 pts:** Basic summary that mentions skills gained but lacks specificity or depth in analyzing personal development. Limited discussion of future contributions. | **0-6 pts:** Summary is missing or inadequate. Few or no specific skills identified. Little evidence of reflection on personal growth. |
| **5. Clarity & Presentation (10 points)** | **9-10 pts:** Exceptionally clear, concise, and well-organized writing. Professional tone. Document is well-formatted and easy to read. Error-free. | **7-8 pts:** Clear and well-organized writing with minor errors. Good formatting that enhances readability. Professional tone throughout. | **5-6 pts:** Writing is understandable but may lack clarity, organization, or professionalism in tone. Formatting may be inconsistent. | **0-4 pts:** Writing is unclear, poorly organized, and difficult to understand. Formatting is poor and detracts from content. |
| **Total (100 points)** | **90-100 pts:** Excellent | **75-89 pts:** Good | **60-74 pts:** Fair | **0-59 pts:** Needs Improvement |