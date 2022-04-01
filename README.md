# Jvav Lint

A tool that format your Jvav code in PERFECT CODE STYLE EVER.

## Usage

```textile
usage: jvav-lint [-h] [-i] file [file ...]

Javav-Lint, a linting tool for Java code.

positional arguments:
  file           The files to lint

options:
  -h, --help     show this help message and exit
  -i, --inplace  Modify the files in place
```

For example, the following command will do lint and replace all java files in current directory.

```shell
python jvav-lint -i *.java
```

## Introduction

Suppose we have `Student.java` with the following content.

```java
public class Student {
    private int ID;
    private String name;

    public Student(int ID, String name) {
        if (ID > 0) {
            this.ID = ID;
        } else {
            this.ID = 0;
        }
        this.name = name;
    }

    public int getID() {
        return ID;
    }

    public String getName() {
        return name;
    }

    public void setName(String name) {
        this.name = name;
    }

    public static void testStudent() {
        Student s1 = new Student(-1, "Mike");
        Student s2 = new Student(0, "Cici");
        Student s3 = new Student(1, "Chen");
    }
}
```

Then run

```shell
python jvav-lint Student.java
```

Then the output will be

```java
public class Student                        {
    private int ID                          ;
    private String name                     ;

    public Student(int ID, String name)     {
        if (ID > 0)                         {
            this.ID = ID                    ;
        } else                              {
            this.ID = 0                     ;}
        this.name = name                    ;}

    public int getID()                      {
        return ID                           ;}

    public String getName()                 {
        return name                         ;}

    public void setName(String name)        {
        this.name = name                    ;}

    public static void testStudent()        {
        Student s1 = new Student(-1, "Mike");
        Student s2 = new Student(0, "Cici") ;
        Student s3 = new Student(1, "Chen") ;}}
```

## Known Issues

- Repeated processing can lead to unexpected results.
