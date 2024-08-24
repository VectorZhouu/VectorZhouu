- 👋 Hi, I’m @VectorZhouu
- 👀 I’m interested in Math,CS
- 🌱 I’m currently learning Math,CS
- 💞️ I’m looking to collaborate on ???
- 📫 How to reach me ???
- 😄 Pronouns: Well
- ⚡ Fun fact: None

<!---
VectorZhouu/VectorZhouu is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->

```c
#include <stdio.h>
#include <stdlib.h>
int main()
{
  printf("HelooWorld");
}
```
```py
from manim import *
class Sample(Scene):
  def construct(self):
    a = Tex("HelloWorld")
    self.play(Write(a))
    self.play(FadeOut(a))
```
The Project that I dev Now:I'm imitating 漫士启示录's video
```py
from manim import *
import numpy as np

class final(Scene):
    def construct(self):
        #self.add(NumberPlane())
        ola = MathTex(r"e^{\pi i}",
                      r" + 1 = 0").scale(3)
        t1 = MathTex(r"0",
                     r"1")
        t2 = MathTex(r"0",
                     r"1")
        t3 = MathTex(r" +1",
                     r" +1",
                     r" +1",
                     r" -5").set_color(RED).scale(2.23)
        t2[0].set_opacity(0.1)
        t2[1].set_opacity(0.1)
        nl = NumberLine(include_numbers=True,color = BLUE)
        nl.numbers.set_color(BLUE)
        num = ValueTracker(1)
        dot = Dot(color = ORANGE)

        t1[0].move_to([-3.5,0,0]).scale(2.5)
        t1[1].move_to([3.5,0,0]).scale(2.5)
        t2[0].move_to([-3.5,0,0]).scale(10)
        t2[1].move_to([3.5,0,0]).scale(10)
        self.play(Write(ola),run_time = 2)
        self.play(Indicate(ola[0],1.2,ORANGE))
        self.play(ola[0].animate.set_color(TEAL))
        self.play(FadeOut(ola))
        self.play(FadeIn(t1[0],t2[0]))
        self.play(FadeIn(t1[1],t2[1]))
        self.play(Indicate(t1[0],1.5,ORANGE))
        self.play(Indicate(t1[1],1.5,BLUE))
        
        # 0 1
        self.play(FadeOut(t1),Write(nl))
        self.play(nl.numbers[7].animate.set_color(ORANGE),run_time = 0.8)
        self.play(nl.numbers[8].animate.set_color(ORANGE),run_time = 2)
        self.play(nl.animate.scale(2))
        dot.move_to(nl.n2p(0)).scale(1.5)
        arrow = always_redraw(lambda: Arrow(start=nl.n2p(0), end=nl.n2p(num.get_value()), buff=0, color = ORANGE))
        t3.move_to([0,2,0])
        self.play(DrawBorderThenFill(arrow),Write(t3[0]),FadeIn(dot))
        self.wait()
        self.play(num.animate.set_value(2),Write(t3[1]))
        self.wait()
        self.play(num.animate.set_value(3),Write(t3[2]))
        self.wait()
        self.play(num.animate.set_value(-2),Write(t3[3]))
        self.wait()
        gr1 = VGroup(nl,t3,t2,arrow,dot)
        self.play(FadeOut(gr1))
        self.wait()

        # i
        i1 = MathTex(r"i").scale(2.5)
        i2 = MathTex(r"i").scale(10).set_opacity(0.1)
        i3 = MathTex(r"i",
                     r" = ",
                     r"\sqrt{-1} ").scale(2.5)
        i3[0].set_color(YELLOW)
        i3[2].set_color(ORANGE)
        i4 = MathTex(r"i ^ 2",
                     r"=",
                     r"-1").scale(2.5)
        i4[0].set_color(YELLOW)
        i4[2].set_color(ORANGE)
        self.play(FadeIn(i2),Write(i1))
        self.play(i1.animate.set_color(YELLOW))
        self.play(i1.animate.move_to([0,2.2,0]))
        self.play(Write(i3))
        self.play(Indicate(i3,1.5,BLUE))
        line = Line(start = i3.get_left(),end = i3.get_right(),color = RED)
        self.play(Write(line))
        self.wait()
        self.play(FadeOut(line),ReplacementTransform(i3,i4))
        self.wait()
        self.play(FadeOut(i1,i2,i4))
        self.wait()

        # e
        e1 = MathTex(r"e").scale(2.5).set_color(TEAL)
        e2 = MathTex(r"e").scale(10).set_opacity(0.1)
        e3 = MathTex(r"e",
                     r"  = \lim_{n \to \infty} \left ( 1 + \frac{1}{n}  \right )^n ").scale(1.45)
        e4 = MathTex(r"({e^x})'=e^x ").scale(2.25)
        e3[0].set_color(TEAL)
        self.play(FadeIn(e2),Write(e1))
        self.wait()
        self.play(TransformMatchingShapes(e1,e3))
        self.wait()
        self.play(e3.animate.to_edge(UL,buff = 1),FadeIn(e4))
        self.play(e4.animate.to_edge(UR,buff = 1).scale(0.7))
        self.play(Indicate(e4,1.4,YELLOW))
        self.wait()
```
And i am developing this to improve my manim animation skills
