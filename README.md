# processing-latex
**Beautiful typesetting with Processing.**

- Thin wrapper around [JLaTeXMath](https://github.com/opencollab/jlatexmath).
- Works in Python mode.
- Still early days. Things will break.

## Example
The following example converts a LaTeX string to a `PShape` object, then displays it.

```java
import latex.*;

void setup() {
  size(680, 163);
  
  String latex = "\\begin{array}{|c|l|||r|c|}";
  latex += "\\hline";
  latex += "\\text{Matrix}&\\multicolumn{2}{|c|}{\\text{Multicolumns}}&\\text{Font sizes commands}\\cr";
  latex += "\\hline";
  latex += "\\begin{pmatrix}\\alpha_{11}&\\cdots&\\alpha_{1n}\\cr\\hdotsfor{3}\\cr\\alpha_{n1}&\\cdots&\\alpha_{nn}\\end{pmatrix}&\\Large \\text{Large Right}&\\small \\text{small Left}&\\tiny \\text{tiny Tiny}\\cr";
  latex += "\\hline";
  latex += "\\multicolumn{4}{|c|}{\\Huge \\text{Huge Multicolumns}}\\cr";
  latex += "\\hline";
  latex += "\\end{array}";
  
  PShape formula = PTeX.toPShape(latex);
  shape(formula, 0, 0);
}
```
