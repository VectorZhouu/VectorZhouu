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

#not callabal的解决方法(Write方法只能用于一个对象)
#用clear_updaters()来取消always_redraw

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
        #line = Line(start = i3.get_left(),end = i3.get_right(),color = RED)
        line = Line([-2.25,0.75,0],[2.25,-0.75,0],color = RED)
        line2= Line([2.25,0.75,0],[-2.25,-0.75,0],color = RED)
        self.play(Write(line),run_time = 0.3)
        self.play(Write(line2),run_time = 0.3)
        self.wait()
        self.play(FadeOut(line,line2),ReplacementTransform(i3,i4))
        self.wait()
        self.play(FadeOut(i1,i2,i4))
        self.wait()
        cp = ComplexPlane().add_coordinates()
        vt = ValueTracker(0)
        vt2= ValueTracker(0)
        vt3= ValueTracker(1)
        vt4= ValueTracker(2)
        dl = always_redraw(lambda: Dot(cp.n2p(1+2j),color = YELLOW_C))
        dl2= always_redraw(lambda: Dot(cp.n2p(-2+1j),color = BLUE_E))
        #dl3 = always_redraw(lambda: Dot(cp.n2p(-1+3j),color = GREEN))
        #dl3 = Dot(cp.n2p(-1+3j),color = GREEN)
        lab = always_redraw(lambda: Tex(r"1+2i").next_to(dl,UR))
        lab2= always_redraw(lambda: Tex(r"-2+i").next_to(dl2,UL))
        #lab3= always_redraw(lambda: Tex(r"-1+3i").next_to(dl3,DR))
        arr1 = always_redraw(lambda: Arrow(cp.n2p(vt.get_value())+cp.n2p(vt2.get_value()*1j),cp.n2p(vt3.get_value())+cp.n2p(vt4.get_value()*1j),buff = 0).set_color(YELLOW_C))
        arr2 = always_redraw(lambda: Arrow(ORIGIN,cp.n2p(-2+1j),buff = 0).set_color(BLUE_E))
        #arr3 = always_redraw(lambda: Arrow(ORIGIN,cp.n2p(-1+3j),buff = 0).set_color(GREEN))
        vg = VGroup(dl,dl2,lab2,arr1,arr2)
        self.play(Write(cp))
        self.play(Write(vg),Write(lab))
        self.wait()
        self.play(cp.animate.scale(1.25))
        t4 = Tex(r"$(1+2i)$",
                 "+",
                 r"$(-2+i)$")
        t5 = Tex("="
                 r"$(1-2)$",
                 "+",
                 r"$(2i-i)$")
        t6 = Tex("="
                 r"$-1$",
                 "+",
                 r"$3i$")
        t4.set_color_by_tex("(1+2i)",ORANGE)
        t4.set_color_by_tex("(-2+i)",GREEN)
        t5.set_color_by_tex("(1-2)",ORANGE)
        t5.set_color_by_tex("(2i-i)",GREEN)
        t6.set_color_by_tex("-1",ORANGE)
        t6.set_color_by_tex("3i",GREEN)
        gr2 = VGroup(t4,t5,t6)
        gr2.arrange(DOWN,buff = 0.5,center=False)
        gr2.move_to([-5,-2,0])
        self.play(Write(t4))
        self.wait()
        #self.play(dl.animate.remove_updater(always_redraw),lab.animate.remove_updater(always_redraw),run_time= 0.1)
        dl.clear_updaters()
        lab.clear_updaters()
        self.play(vt.animate.set_value(-2),vt2.animate.set_value(1),vt3.animate.set_value(-1),vt4.animate.set_value(3),dl.animate.move_to(cp.n2p(-1+3j)),FadeOut(lab),Write(t5))
        self.wait()

        dl3 = Dot(cp.n2p(-1+3j),color = GREEN)
        lab3= Tex(r"-1+3i").next_to(dl3,DR)
        arr3 = Arrow(ORIGIN,cp.n2p(-1+3j),buff = 0).set_color(GREEN)
        self.play(Write(dl3),Write(lab3),Write(arr3),Write(t6))
        self.wait()
        self.play(FadeOut(vg,cp,arr3,dl3,lab3,gr2))
        #self.play(FadeOut(dl3),FadeOut(vg),FadeOut(cp),FadeOut(arr3),FadeOut(lab3))

        # e
        e1 = MathTex(r"e").scale(2.5).set_color(TEAL)
        e2 = MathTex(r"e").scale(10).set_opacity(0.1)
        e3 = MathTex(r"e",
                     r"= \lim_{n \to \infty} \left ( 1 + \frac{1}{n}  \right )^n ").scale(1.45)
        e4 = MathTex(r" ({e ^x})'= e ^x ").scale(2.25)
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
