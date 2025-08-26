- 👋 Hi, I’m VectorZhouu
- 👀 I’m interested in Math,CS
- 🌱 I’m currently learning Math,CS






![Typing SVG](https://readme-typing-svg.demolab.com/?lines=What+I+am+deving?+Might+about+these+things:;Math;Computer+Science;Computer+Vision;Python+Game;Android+Studio)
<br>
![Anurag's GitHub stats](https://github-readme-stats.vercel.app/api?username=VectorZhouu&show_icons=true&theme=holi)
<br>
![GitHub Streak](https://streak-stats.demolab.com/?user=VectorZhouu)
<br>
![暗色](https://raw.githubusercontent.com/VectorZhouu/VectorZhouu/output/github-contribution-grid-snake-dark.svg)
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
The Project that I dev Now:I'm imitating 漫士启示录's video(Run on ManimCommunityEdition)
```py
from manim import *
import numpy as np

#not callabal的解决方法(Write方法只能用于一个对象)
#用clear_updaters()来取消always_redraw
#class test用以快速测试函数
#valuetracker报错请用get_value()来取值

class final(Scene):
    def construct(self):
        #self.add(NumberPlane())
        #shuiyin = Tex(r"17d615c").set_opacity(0.01).scale(2.54).to_edge(UL,buff = 0.5)
        olach = Text("欧拉恒等式",weight=BOLD).set_color_by_gradient("#f6d365","#fda085")
        olaen = Text("Euler's identity",slant=ITALIC).set_color_by_gradient("#43e97b","#38f9d7")
        grola = VGroup(olach,olaen)
        ola = MathTex(r"e^{\pi i}",r" + 1 = 0").scale(3)
        t1 = MathTex(r"0",r"1")
        t2 = MathTex(r"0",r"1")
        t3 = MathTex(r" +1",r" +1",r" +1",r" -5").set_color(RED).scale(2.23)
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
        self.play(Write(olach))
        self.play(olach.animate.move_to([0,2.5,0]))
        grola.arrange(DOWN,buff = 0.5,center=False)
        self.play(Write(olaen))
        self.play(Write(ola),run_time = 2)
        self.play(Circumscribe(ola))
        self.play(Indicate(ola[0],1.2,ORANGE))
        self.play(ola[0].animate.set_color(TEAL))
        self.play(FadeOut(ola,grola))
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
        i3 = MathTex(r"i",r" = ",r"\sqrt{-1} ").scale(2.5)
        i3[0].set_color(YELLOW)
        i3[2].set_color(ORANGE)
        i4 = MathTex(r"i ^ 2",r"=",r"-1").scale(2.5)
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
        self.play(FadeOut(i1,i4))
        cpten = Text("Complex").set_color_by_gradient("#fa709a","#fee140")
        cptch = Text("复平面").set_color_by_gradient("#fddb92","#d1fdff")
        self.play(Write(cptch))
        self.play(cptch.animate.move_to([0,2,0]))
        grcp = VGroup(cptch,cpten)
        grcp.arrange(DOWN,buff = 0.5,center=False)
        self.play(Write(cpten))
        self.wait()
        self.play(FadeOut(grcp))
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
        vecch = Text("向量").set_color_by_gradient(GREEN,BLUE)
        vecen = Text("Vector").set_color_by_gradient(YELLOW,ORANGE)
        vecgr = VGroup(vecch,vecen)
        self.play(Write(cp),Write(vecch))
        self.play(vecch.animate.move_to([0,2,0]))
        vecgr.arrange(DOWN,buff = 0.5,center=False)
        self.play(Write(vecen))
        self.play(FadeOut(vecgr))
        self.play(Write(vg),Write(lab))
        self.wait()
        self.play(cp.animate.scale(1.25))
        t4 = Tex(r"$(1+2i)$","+",r"$(-2+i)$")
        t5 = Tex("=",r"$(1-2)$","+",r"$(2i-i)$")
        t6 = Tex("=",r"$-1$","+",r"$3i$")
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
        self.play(FadeOut(vg,cp,arr3,dl3,lab3,gr2,i2))
        #self.play(FadeOut(dl3),FadeOut(vg),FadeOut(cp),FadeOut(arr3),FadeOut(lab3))

        # e
        e1 = MathTex(r"e").scale(2.5).set_color(TEAL)
        e2 = MathTex(r"e").scale(10).set_opacity(0.1)
        e3 = MathTex(r"e",r"= \lim_{ n \to \infty} \left ( 1 + \frac{1}{n}  \right )^n ")
        e4 = MathTex(r" ({e ^x})'= e ^x ")
        #e5 = MathTex(r"f(x)="
        #             r"k"
        #             r"e^x")
        #e5.move_to([-4,4,0])
        #k = ValueTracker(1)
        gr3 = VGroup(e3,e4)
        e3[0].set_color(TEAL)
        #e5[1].set_color(GREEN_C)
        #e3.set_color_by_tex("n",TEAL)
        gr3.scale(1.25)
        #e3[0].set_color(TEAL)
        self.play(FadeIn(e2),Write(e1))
        self.wait()
        gr3.arrange(RIGHT,buff = 5,center=False)
        self.play(TransformMatchingShapes(e1,e3))
        self.wait()
        self.play(gr3.animate.to_edge(UL,buff = 0.5))
        #self.play(e3.animate.to_edge(UL,buff = 1),FadeIn(e4))
        #self.play(e4.animate.to_edge(UR,buff = 1).scale(0.7))
        #self.play(Indicate(e4,1.4,YELLOW))
        self.wait()
        npl = NumberPlane()
        k = ValueTracker(1)
        fuen = Text("Exponential function").set_color_by_gradient("#d4fc79","#96e6a1")
        fuch = Text("指数函数").set_color_by_gradient("#84fab0","#8fd3f4")
        fugr = VGroup(fuch,fuen)
        num1 = always_redraw(lambda: DecimalNumber(k.get_value(),num_decimal_places=0).move_to([-4,3,0]))
        func = lambda x:  k.get_value() * np.exp(x)
        gra1 = always_redraw(lambda: npl.plot(func,color = GREEN))
        #dot1 = Dot(gra1.get_start())
        self.play(FadeOut(gr3))
        self.play(Write(fuch))
        self.play(fuch.animate.move_to([0,2,0]))
        fugr.arrange(DOWN,buff = 0.5,center=False)
        self.play(Write(fuen))
        self.play(FadeOut(fugr))
        self.play(Write(npl))
        self.play(Write(gra1))
        self.play(Write(num1))
        #self.play(MoveAlongPath(dot1, gra1), run_time=5)
        self.play(k.animate.set_value(5),run_time = 3)
        self.play(k.animate.set_value(-10),run_time = 3.8)
        self.wait()
        self.play(FadeOut(num1,gra1,npl,e2))

        # pi
        achien = Paragraph("Dont disturb my circles (Archimedes probably said:",
                       " Noli turbare circulos meos!)").set_color_by_gradient(GREEN,BLUE)
        achich = Text(r"别碰我的圆!!!").set_color_by_gradient(GREEN,BLUE).scale(0.9)
        achen  = Tex(r"----Archimedes").set_color_by_gradient(GREEN,BLUE).scale(1.5)
        achch  = Text(r"--阿基米德").set_color_by_gradient(GREEN,BLUE).scale(0.9)
        achien.to_edge(UP,buff = 0.4)
        achen.next_to(achien,DR,buff = 0.15)
        achengr = VGroup(achien,achen)
        achich.next_to(achengr,DOWN,buff = 0.5)
        achch.next_to(achich,DR,buff = 0.15)
        achchgr = VGroup(achich,achch)
        achgr = VGroup(achengr,achchgr).scale(0.65).arrange(DOWN,center=False).to_edge(UL,buff = 1)

        pi1 = MathTex(r"\pi").set_color(GREEN).scale(2.5)
        pi2 = MathTex(r"\pi").set_opacity(0.1).scale(10)
        self.play(Write(pi1),FadeIn(pi2))
        self.play(Write(achgr),pi1.animate.to_edge(DOWN,buff = 0.5))
        self.play(ApplyWave(pi1))
        self.wait()
        self.play(FadeOut(achgr),pi1.animate.to_edge(UL,buff = 1))
        #whatpi = Paragraph(
        #    "What is the π?",
        #    "什么是π?"
        #).set_color_by_gradient("#96fbc4","#f9f586")
        whatpien = Tex(r"$What \ is \ the \ \pi ?$").set_color_by_gradient(("#96fbc4","#f9f586")).scale(1.21)
        what  = Text("什么是").set_color_by_gradient("#96fbc4","#f9f586")
        pi = Tex(r"$ \pi ? $").set_color("#f9f586").scale(2)
        whatpich = VGroup(what,pi)
        whatpich.arrange(RIGHT).scale(0.9)
        whatpi = VGroup(whatpien,whatpich)
        whatpi.arrange(DOWN,buff = 0.5)
        
        self.play(Write(whatpi),ApplyWave(pi1))
        self.play(FadeOut(whatpi))
        #c = Circle(radius=1,color = "#ff1eb",fill_opacity = 1)
        dl4 = Dot([0,0,0],color=RED)
        c = Circle(stroke_width=2,radius=2,fill_opacity = 0.1).set_color_by_gradient("#fff1eb","#ace0f9")
        self.play(GrowFromCenter(c),FadeOut(pi1))
        self.wait()
        #s = Text("S = πr²").set_color_by_gradient("#c1dfc4","#deecdd")
        #s = Text(r"S = πr²").set_color_by_gradient(ORANGE,YELLOW)
        #cc= Text("C = 2πr").set_color_by_gradient("#74ebd5","#9face6")
        s = Tex(r"$S = \pi r^2$").set_color_by_gradient("#c1dfc4","#deecdd")
        cc= Tex(r"$C = 2 \pi r$").set_color_by_gradient("#74ebd5","#9face6")
        sc = VGroup(s,cc)
        sc.arrange(DOWN,buff = 0.5,center=False).move_to([-3.5,0,0])
        #c.set_fill_opacity(0.1)
        r = DashedLine([0,0,0],[2,0,0],buff = 0,color = RED,stroke_width = 3)
        rten = Tex(r"radius").set_color(ORANGE).scale(1.21)
        rtch = Text("半径").set_color(ORANGE).scale(0.9)
        rt = VGroup(rten,rtch).scale(0.9)
        rt.arrange(DOWN,buff = 0.5).next_to(r,UP,buff = 0.5)
        self.play(Write(r),Write(dl4),Write(rt))
        self.play(Write(sc))
        circ = VGroup(c,dl4,r,rt)
        self.play(Rotate(circ,angle=2*PI))
        self.wait()
        self.play(FadeOut(rt,dl4,r,sc))
        cp.scale(0.8)
        unitch = Text(r"复平面上的单位圆").set_color_by_gradient("#0dcda4","#c2fcd4")
        unit = Text("A unit circle on a complex plane").set_color_by_gradient("#0dcda4","#c2fcd4")
        self.play(FadeOut(c),Write(unit))
        self.play(FadeOut(unit),GrowFromCenter(c))
        self.play(c.animate.scale(0.5),Write(cp))
        cpc = VGroup(cp,c)
        self.play(cpc.animate.scale(3))
        ori = Dot(cp.n2p(0),color=TEAL)

        #cvt1 = ComplexValueTracker()
        #vt1 = ValueTracker(0)
        theta = ValueTracker(0)
        #cosx = always_redraw(lambda: np.cos(theta.get_value()))
        #sinx = always_redraw(lambda: np.sin(theta.get_value()))
        #vt2.set_value(0)
        arr4 = always_redraw(lambda: Arrow(cp.n2p(0),cp.n2p(np.cos(theta.get_value()) + np.sin(theta.get_value()) * 1j),buff = 0,color = ORANGE))
        arrcos=always_redraw(lambda: Arrow(cp.n2p(0),cp.n2p(np.cos(theta.get_value())),buff = 0,color = BLUE))
        arrsin=always_redraw(lambda: Arrow(cp.n2p(np.cos(theta.get_value())),cp.n2p(np.cos(theta.get_value()) + np.sin(theta.get_value()) * 1j),buff = 0,color =GREEN))
        tcos = always_redraw(lambda: MathTex(r" \cos \left ( \theta  \right ) ").next_to(arrcos,DOWN,buff = 0.25))
        tsin = always_redraw(lambda: MathTex(r" \sin \left ( \theta  \right ) ").next_to(arrsin,RIGHT,buff = 0.25))
        tvec =always_redraw(lambda: MathTex(r" \cos \left ( \theta  \right ) + i\sin \left ( \theta  \right ) "))
        self.play(Write(arr4),Write(arrcos),Write(arrsin),Write(tcos),Write(tsin))
        self.play(theta.animate.set_value(120 * DEGREES),run_time = 2)
        self.wait()
        self.play(theta.animate.set_value(-45 * DEGREES),run_time = 2)
        
    
        #vt2.set_value(0)
        #cvt1 = ComplexValueTracker()
        #cvt1.set_value(vt1.get_value() + vt2.get_value()*1j)
        #arr4 = always_redraw(lambda: Arrow(cp.n2p(0),cp.n2p(cvt1.get_value()))).set_color(ORANGE)
        #self.play(Write(arr4))
        #self.play(theta.animate.set_value(100 * DEGREES))
        #self.play(vt1.animate.set_value(np.cos(theta)),vt2.animate.set_value(np.sin(theta)))
        




        #重新用vt的valuetracker
        #vt.set_value(0)
        #a = Angle(m , mm, radius=0.5, other_angle=False)
        #m = Line(cp.n2p(0),cp.n2p(1),buff = 0)
        #mm= Line(cp.n2p(0),cp.n2p(1),buff=0)
        #self.play(Write(m),Write(mm))
        #self.play(vt.animate.set_value(120))
        #a.add_updater(
        #    lambda x: x.become(Angle(m,mm, radius=0.5, other_angle=False))
        #)
        #self.play(mm.animate.rotate(vt.get_value()*DEGREES,about_point=cp.n2p(0)))
        #k.set_value(0)
        #vt5 = ValueTracker(0)
        #sinx = always_redraw(lambda: np.sin(vt5))
        #cosx = always_redraw(lambda: np.cos(vt5))
        #gra2 = Line(ORIGIN,cp.n2p(cosx + sinx * 1j))
        #self.play(Write(ori),Write(gra2))
        #self.play(k.animate.set_value(7))
        self.wait()



        #self.play(FadeOut(shuiyin))
```
And i am developing this to improve my manim animation skills
<br>
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=VectorZhouu&layout=compact)](https://github.com/anuraghazra/github-readme-stats)
<br>
![Ashutosh's github activity graph](https://github-readme-activity-graph.vercel.app/graph?username=VectorZhouu)


