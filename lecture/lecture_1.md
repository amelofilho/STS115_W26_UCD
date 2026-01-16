# Lecture 1: 1/9

### CLI Intro:

### Commands:

- **cd**
    - cd ~
- **ls**
    - Flags
        - `-a` 
        - `-l` lists info about files inside dir (read/write acccess, permissions)
- **mkdir**
    - `mkdir <dir_name>`
- **vim <file_name> (or pico/emacs/nano)**
    - esc until normal mode
- **rm**
    - rmdir removes directories
    - rm for files
    - Flags 
        - `-r -f` removes forcefully
- **cp**
    - copies file `cp <source> <destination>`q
    - Flags 
        - `- R` to copy repos
- **history**
    - displays the last 500 commands entered in terminal (500 by default on mac)

### Vim Commands:
- `:wq` to write & quit or `:w` + `:q` seperately works


### Research:

- Process of systematic inquiry involving:
    - collect data
    - document crit info
    - analyze + interpret data

- Helps us make decisions/ solve sometihng...
    - form opinions/back them up

- Why should we care ab research?
    - critical thinking, problem solving & soft skills

**Research Lifecycle**

- Research types are diff, but they follow similar procedures
- Research starts & ends w/ why
- Cycle
    1. Create proposal/DMP
    2. Collect,store & document data
    3. inspect, eval, process & select
    4. analyze & interpret
    5.
    6. 
    7. 

### Reproducability: 

- Ability to repeat same analysis w same data and get diff results
- Why does this matter?
    - independent verification
    - distribute and adopt
    - collab
    - revisit and reuse work

**1. Documentation**
- Writing is main mech for research
- It increases scientific rigor:
    - Forces you to slow down
    - Helps remember and use details
    - Facilitates connections
- Document everything (graph slide)
- Write READMEs
    - File explains the project
- Document the data
    - what was collected
    - assumptions made (biases, etc)
    - metadata explaining collection processing method and data structures used

**2. Project Organization**
- Established a directory structure
- Using naming conventions
    - should be: descriptive, humaan/machine readble, sorts well
        - Avoid uppercase, spaces/punc, 
        - Use IOS 8601 format, pad numbers, dates
- Save clean data seperately (og data)
    - keep a copy of original, clean data to traceback if needed

**3. Artifact Preservation**
- Every file you produce is an artifact of your research
- Make backups
    - 3, 2, 1 back up rule:
        1. Main 3 copies of your data
        2. Store backup ...
        3. ...
- Use version control systems 
    - like Github

**4. Workflow Automation**
- A workflow is a way of carrying our a set of tasks
- Compute w code
    - Using R, python


### Structure for all HWs:
    .
    └── hw_#
       ├── data
       ├── docs
       ├── figures
       └── R


## Assignments:
- Getting to know you quiz
- HW1
    - Due 1/23
