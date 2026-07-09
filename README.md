# 

### Project Structure:

    JavaBasics_Task_539/
    ├─ src/main/java/com/yurii/pavlenko/
    │                          ├── model/
    │                          │   └── Task.java
    │                          ├── repository/
    │                          │   └── TaskRepository.java
    │                          ├── service/
    │                          │   └── TaskService.java
    │                          ├── component/
    │                          │   └── TaskPrinter.java
    │                          ├── config/
    │                          │   └── AppConfig.java
    │                          └── Main.java
    ├── pom.xml
    ├── LICENSE
    ├── TASK.md
    ├── THEORY.md
    └── README.md

## 💻 Code Example

```java
package com.yurii.pavlenko;

import com.yurii.pavlenko.config.AppConfig;
import com.yurii.pavlenko.model.Task;
import com.yurii.pavlenko.service.TaskService;
import com.yurii.pavlenko.component.TaskPrinter;
import org.springframework.context.annotation.AnnotationConfigApplicationContext;

/**
 * Main entry point.
 */
public class Main {
    public static void main(String[] args) {

        AnnotationConfigApplicationContext context = new AnnotationConfigApplicationContext(AppConfig.class);

        TaskService taskService = context.getBean(TaskService.class);
        TaskPrinter taskPrinter = context.getBean(TaskPrinter.class);

        taskService.saveTask(new Task("Learn Spring"));
        taskService.saveTask(new Task("Master Dependency Injection"));
        taskService.saveTask(new Task("Finish the project"));

        taskPrinter.printAll();

        context.close();
    }
}
```

## ⚖️ License
This project is licensed under the **MIT License**.

Copyright (c) 2026 Yurii Pavlenko

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files...

License: [MIT](LICENSE)
