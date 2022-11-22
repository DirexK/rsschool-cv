# CV-Проект
### Александр Головей

Мои контакты. Почта - alex.gol.01@inbox.ru

>Я студент _**БрГУ им. А.С.Пушкина**, **физико-математического**_ факультета специальности _**Прикладная Математика**_.
>За **4 года**, которые провёл в университете, я изучил большое количество __разнообразных языков программирования__.
>Я каждый день узнаю, что-то новое бывает такое, что принимаю лабораторные работы у младших курсов.

>Я знаком с многим количеством языком программирования, такие как **C++, Java, C#, JavaScripts, Python и др.**. В основном я программирую
>на языке _**Java**_ для работы с приложениями и _**JavaScripts**_ для работы с Web-приложениями. Также работал с Базами Данных, которые я разробатывал на _**PHPMyAdmin и MySQL WorkBench**_.
>Также был опыт работы с библиотекой **React**.


### Пример Кода
    import javax.swing.*;
    import java.awt.*;
    import java.util.Scanner;

    public class Main {
    public static void main(String[] args) {

        double mu = 9 * Math.pow(10, -9);
        double mg = 9.80;
        double[] v = new double[1000];

        Scanner sc = new Scanner(System.in);
        System.out.println("Введите значения через Enter: m, v_0, delta_t, T");

        double m = sc.nextDouble();
        double v_0 = sc.nextDouble();
        double delta_t = sc.nextDouble();
        int T = sc.nextInt();

        double V = v_0 * Math.exp(-(mu/m)*(T/delta_t)) ;    //АНАЛИТИЧЕСКОЕ РЕШЕНИЕ
        System.out.println("V = " + V);

        for (int i = 1; i < (T/delta_t); i++) {
            double Fc = -mu * V;
            System.out.println("Fc = " + Fc);
            v[0] = v_0;
            v[i] = v[i-1] - (mu / m) * v[i-1] * delta_t;    //РАЗНОСТНЫЙ АНАЛОГ УРАВНЕНИЯ ДВИЖЕНИЯ
            System.out.println(i + " : " + v[i]);
            double KOSHI =+ mg + Fc - m * v[i];             //РЕШЕНИЕ KOSHI
            System.out.println(KOSHI);
        }



        double Fc = -mu * V;
        System.out.println("Fc = " + Fc);

        JFrame jf = new JFrame();
        jf.setSize(1000, 1000);
        jf.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        Canvas canvas = new Canvas();
        canvas.setData(v, delta_t, m);
        jf.add(canvas);
        jf.setVisible(true);

        }
    }


    class Canvas extends JComponent {

            private double[] v;
            private double delta_t;
            private double m;
            public void paintComponent(Graphics g) {
                super.paintComponent(g);
                Graphics2D g2d = (Graphics2D) g;
                g2d.setPaint(Color.GREEN);
                for (int i = 0; i < v.length-1; i++) {
                    g2d.setPaint(Color.GREEN);
                    g2d.drawLine(i * Math.round((float) delta_t*10), Math.round((float) ((v[i]*10))), (i + 1) * Math.round((float) delta_t*10), Math.round((float) ((v[i+1]*10))));
                    g2d.setPaint(Color.BLUE);
                    g2d.drawLine(i * Math.round((float) delta_t*10), Math.round((float)(v[0]*Math.exp(-6.67 * (0.00000000001/m)*i*delta_t)*10)),(i + 1) * Math.round((float) delta_t*10), Math.round((float)(v[0]*Math.exp(-6.67 * 0.00000000001/m*(i+1)*delta_t)*10)));
                }
                super.repaint();
            }


            public void setData(double[] v, double delta_t, double m) {
                this.v = v;
                this.delta_t = delta_t;
                this.m=m;
            }

        }


>Мой уровень **айнглийского языка A2 - B1**. Английский я изучал только в ГУО и прохождением курсов по английскому языку.
>Был опыт разговора с носителем английского языка в переписке в социальных сетях.
