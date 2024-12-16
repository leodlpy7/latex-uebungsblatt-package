
# Uebungsblatt - A latex package

The `uebungsblatt` package can be used for pretty exercise sheets. There are a few environments defined, which are explained inside the documentation (coming soon). For now, there is an example of how to use the package.

Please note, that this package contains hard-coded parts, which are in german. If you wich to have another language, you have to go inside the source code and change the parts manually.

## How to use

Here is an example of how to use the environments defined inside the package:

```tex
\documentclass{article}
\usepackage{uebungsblatt}
\usepackage{lipsum}
\begin{document}
    % set all parameters for the exercise sheet
    \setUebungsblattParams[
        name=John Doe, % your name
        matrikelnr=1234567, % your matriculation number
        dozent=Jenny Doe, % your lecturer
        modul=Anatomy, % your lecture
        university=Universidad de los muertos, % your university
        semester=Wintersemester 2024/25, % the semester
        semestershort=WiSe 24/25, % the abbreviation of the semester
        uebungsblattnr=1, % the exercise sheet number
        aufgabennr=0 % the exercise number to start the exercise sheet,
        % because of implementation details, you have to subtract one
    ]{}
    % build the style of the exercise sheet
    \makeUebungsblattStyle{}

    % now begin with the exercises
    % the first parameter is the exercise name, the second the points you can get
    \begin{exercise}{Exercise Name}{10}
        \lipsum[1]
        % you can define subtasks ...
        \begin{subtasks}
            % ... with the subtasks written down in their own environment
            \begin{subtask}{3}
                \lipsum[1]
            \end{subtask}
            \begin{subtask}{3}
                \lipsum[1]
            \end{subtask}
        \end{subtasks}
    \end{exercise}
    % and of course you can give the solution of the exercise
    \begin{solution}
        % with all subtasks like above
        \begin{subtasks}
            \begin{subtask}{}
                \lipsum[1]
            \end{subtask}
            \begin{subtask}{}
                \lipsum[1]
            \end{subtask}
        \end{subtasks}
    \end{solution}
\end{document}
```

The compiled result of the code above can be found in this repository.

## License

The code within this repository is licensed under the terms of the MIT license.

```
Copyright 2024 Leonard Delpy

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the “Software”), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies
of the Software, and to permit persons to whom the Software is furnished to do
so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED,
INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A
PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT
HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION
OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE
SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
```