# Lab 4: UML, GitHub Project and Issues


In this lab, you will gain hands-on experience creating UML class diagrams from existing Java code using graphical diagramming tools such as **draw.io**, as well as generating diagrams programmatically with **Mermaid** syntax. This lab assignment will strengthen your ability to visually communicate object-oriented designs, and enhance your project management skills by utilizing GitHub projects and issues, including creating, organizing, and writing clear, actionable issues to manage development tasks efficiently.


## The Code

The code provided below represents a simple Java application that models an animal hierarchy. You will be creating UML class diagrams based on this code.

### Abstract Animal Class
```java
public abstract class Animal {
    private String name;

    public Animal(String name) {
        this.name = name;
    }

    public String getName() {
        return name;
    }

    public abstract String makeSound();
}
```

### Dog Class
```java
public class Dog extends Animal {
    private String breed;
    
    public Dog(String name, String breed) {
        super(name);
        this.breed = breed;
    }
    
    public String getBreed() {
        return breed;
    }
    
    @Override
    public String makeSound() {
        return "Woof!";
    }
    
    public void fetch() {
        System.out.println(getName() + " is fetching!");
    }
}
```

### Cat Class
```java
public class Cat extends Animal {
    private int lives;
    
    public Cat(String name) {
        super(name);
        this.lives = 9;
    }
    
    public int getLives() {
        return lives;
    }
    
    public void loseLive() {
        if (lives > 0) {
            lives--;
        }
    }
    
    @Override
    public String makeSound() {
        return "Meow!";
    }
}
```

### Bird Class
```java
public class Bird extends Animal {
    private boolean canFly;
    
    public Bird(String name, boolean canFly) {
        super(name);
        this.canFly = canFly;
    }
    
    public boolean getCanFly() {
        return canFly;
    }
    
    @Override
    public String makeSound() {
        return "Tweet!";
    }
    
    public void fly() {
        if (canFly) {
            System.out.println(getName() + " is flying high!");
        } else {
            System.out.println(getName() + " cannot fly!");
        }
    }
}
```


## Tasks

### Task 1: Accept the GitHub Organization Invitation

You should have recieved an email invitation to join the UC3093C GitHub organization.  Accept the invitation to join the organization. You will need to be a member of this organization to complete the lab.

<br>

```{image} /images/github_uc3093c_invite.png
:alt: fishy
:width: 200px
:align: center
```

<br>

If you have not received this email, please check your spam folder.  If you still do not see it, please contact me.

### Task 2: Accept GitHub Classroom Assignment

Accept the the following GitHub Classroom assignment invitation, this will create a personal repository in the UC3093C organization.  You will be using this repository to manage your project and submit your work.

[https://classroom.github.com/a/w13UuPS-](https://classroom.github.com/a/w13UuPS-)


### Task 3: Create GitHub Project Board

Create a GitHub project board in your repository to manage your tasks, you must use the Kanban template.  The name of the project should be your GitHub username followed by "Lab 4".  For example, "@loudinb's Lab 4".

You must modify the board to have only the following columns:

- To-Do
- In Progress
- Done

### Task 4: Add Items to the Project Board

Create two items in the "To-Do" column of your project board.  These items will represent the tasks you will be completing in this lab.  You will name these items as follows:

1) "Create UML class diagram using draw.io"
2) "Create UML class diagram using Mermaid"


```{warning}
You must create these items as issues which are linked to your GitHub repository.  Read the instructions carefully to ensure you are creating issues properly.
```

You can create these items by clicking on the "+ Add-Item" icon in the "To-Do" column.  Select the option to "Create new issue". In the dialog that appears, select the GitHub repository created for Lab 4.

<br>

```{image} /images/github_project_create_new_issue.png
:alt: fishy
:width: 600px
:align: center
```

<br>
 
Select the "Blank issue" option and then complete the issue using the following markdown template for your issue description, just copy and paste into your issue description (make sure to make minor adjustments to the template to fit your specific task).

```
## Description
Create a UML class diagram that accurately represents the Animal class hierarchy using [draw.io OR Mermaid].

## Requirements
- Represent all four classes: Animal, Dog, Cat, and Bird
- Show all attributes with proper visibility notation
- Show all methods with proper visibility notation
- Include return types and parameters for methods
- Properly indicate the abstract class and abstract method
- Show all inheritance relationships
- Follow standard UML notation

## Acceptance Criteria

- [ ] All classes are correctly represented
- [ ] All attributes are shown with proper visibility
- [ ] All methods are shown with proper visibility
- [ ] Abstract class and method are properly indicated
- [ ] Inheritance relationships are correctly shown
- [ ] Diagram is committed to the repository as [image file or markdown file]
```

When creating the issue you must:

- Use the issue template (in markdown syntax) provided above.  
- Assign the issues to yourself.
- Add "documentation" as a label.
- Add "UML" as a label, but you will need to create this label first. Use "UML" as the name and "UML diagrams" for the description.
- Specify "Task" as the issue type.

When viewed from the project board, an issue should look like this:

<br>

```{image} /images/github_issue.png
:alt: fishy
:width: 600px
:align: center
```

<br>

### Task 5: Visual UML Class Diagram with draw.io

1. Move this issue to "In Progress" in your Kanban board
2. Create a complete UML class diagram using draw.io that represents all four classes in the code
3. Export the diagram as a PNG or JPEG file
4. Commit this file to your repository with the message "Completed UML class diagram in draw.io - fixes #X" (where X is your issue number)
5. Move the issue to "Done" in your Kanban board

### Task 6: Code-based UML Class Diagram with Mermaid

1. Move this issue to "In Progress" in your Kanban board
2. Create a markdown file in your repository named `UML-class-diagram.md`
3. Use Mermaid syntax to create the class diagram in this file
4. Commit the file with the message "Completed UML class diagram in Mermaid - fixes #Y" (where Y is your issue number)
5. Move the issue to "Done" in your Kanban board


## Additional Information

### Linking Issues to Commits

When you commit your changes, you should include the issue number in the commit message. This will help you track which commits are related to which issues. For example, if you are working on issue #1, you can include "#1" in your commit message. This will create a link between the commit and the issue, making it easier to track progress and see which issues have been resolved.

There are special keywords that you can use in your commit messages to automatically close issues when the commit is pushed to the main branch. For example, if you want to close issue #1 when you push your commit, you can include the keyword "fixes" followed by the issue number in your commit message. For example, you can write:

```
git commit -m "Completed UML class diagram in draw.io - fixes #1"
```

This will automatically close issue #1 when the commit is pushed to the main branch.

See [GitHub documentation](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/using-keywords-in-issues-and-pull-requests) for more information on closing issues with commit messages.

### Mermaid

[Mermaid](https://mermaid.js.org) is a JavaScript-based diagramming and charting tool that uses Markdown-inspired syntax. It allows you to create diagrams and visualizations directly in your markdown files. 

Mermaid supports various types of diagrams, including flowcharts, sequence diagrams, and class diagrams. In this lab, you will use Mermaid to create a class diagram that represents the same classes and relationships as in the draw.io diagram.  Please see the [Mermaid class diagram documentation](https://mermaid.js.org/syntax/classDiagram.html) for more details on syntax and features.

GitHub supports rendering Mermaid diagrams directly in markdown files, so you can include your class diagram in the `UML-class-diagram.md` file you create.

## Grading

### Deliverables

1. A GitHub repository containing:
   - PNG/JPEG file of your draw.io UML class diagram
   - A markdown file named `UML-diagram.md` with Mermaid code for the class diagram
2. GitHub Issues that are properly closed by your commits from the commit message, for example, "Create UML class diagram using draw.io fixes #1"
3. A completed GitHub Project board showing your workflow progression (both tasks should be in the "Done" column)

### Following proper UML notation guidelines

1. **Class Representation**:
   - Regular classes: Rectangle with solid lines
   - Abstract classes: Rectangle with solid lines, class name in *italics*

2. **Visibility Modifiers**:
   - Public: +
   - Private: -
   - Protected: #
   - Package: ~ (no modifier)

3. **Methods**:
   - Format: visibility name(parameters): returnType
   - Abstract methods should be in *italics*

4. **Attributes**:
   - Format: visibility name: type

5. **Inheritance**:
   - Shown with an arrow pointing from the subclass to the superclass
   - Use a solid line with a hollow triangular arrowhead


### Grading Rubric

- Correct representation of classes and relationships in class diagram, proper use of UML notation for visibility, abstract classes, and methods (50%)
  - Correct implementation using draw.io diagram (25%)
  - Correct implementation using Mermaid diagram (25%)
- Proper use of GitHub Project and Issues with correct issue template (50%)
  - Created a project board with the correct columns (5%)
  - Correctly created both GitHub Issues - name, description, assignee, labels, type (20%)
  - Isuues linked to your GitHub repository and a proper commit message to automaticaly close the issue (moving it to Done). (25%)