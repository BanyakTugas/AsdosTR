# AsdosTR
#include<windows.h>
#include <GL/Glut.h>

void init(void);
void tampil(void);
void mouse(int button, int state, int x, int y);
void ukuran(int, int);
void mouseMotion(int x, int y);

float xrot = 0.0f;
float yrot = 0.0f;
float xdiff = 0.0f;
float ydiff = 0.0f;
bool mouseDown = false;
int is_depth;

int main(int argc, char** argv)
{
    glutInit(&argc, argv);
    glutInitDisplayMode(GLUT_DOUBLE | GLUT_RGB);
    glutInitWindowSize(800, 600);
    glutInitWindowPosition(250, 80);
    glutCreateWindow("Hizkia Nathanael - 672019047");
    init();
    glutDisplayFunc(tampil);
    glutMouseFunc(mouse);
    glutMotionFunc(mouseMotion);
    glutReshapeFunc(ukuran);
    glutMainLoop();
    return 0;
}

void init(void)
{
    glClearColor(0.0, 0.0, 0.0, 0.0);
    glEnable(GL_DEPTH_TEST);
    glEnable(GL_COLOR_MATERIAL);
    glEnable(GL_LIGHT0);
    glEnable(GL_DEPTH_TEST);
    is_depth = 1;
    glMatrixMode(GL_MODELVIEW);
    glPointSize(9.0);
    glLineWidth(6.0f);

}

void tampil(void)
{
    if (is_depth)
           glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
       else
           glClear(GL_COLOR_BUFFER_BIT);


    glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
    glLoadIdentity();
    gluLookAt(0.0f, 0.0f, 3.0f, 0.0f, 0.0f, 0.0f, 0.0f, 1.0f, 0.0f);
    glRotatef(xrot, 1.0f, 0.0f, 0.0f);
    glRotatef(yrot, 0.0f, 1.0f, 0.0f);
    glPushMatrix();

    //UKSWLogodepan
    glBegin(GL_QUADS);
    glColor3ub(255,222,173);
    glVertex3f(-25, 12, 60.0);
    glVertex3f(-25, 2, 60.0);
    glVertex3f(0, 2, 60.0);
    glVertex3f(0, 12, 60.0);
    glEnd();

    glBegin(GL_QUADS);//tianglogo1
    glColor3ub(47,79,79);
    glVertex3f(-25, 0, 62.0);
    glVertex3f(-25, 16, 62.0);
    glVertex3f(-29, 16, 62.0);
    glVertex3f(-29, 0, 62.0);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-25, 0, 62.0);
    glVertex3f(-25, 16, 62.0);
    glVertex3f(-25, 16, 58.0);
    glVertex3f(-25, 0, 58.0);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-29, 0, 62.0);
    glVertex3f(-29, 16, 62.0);
    glVertex3f(-29, 16, 58.0);
    glVertex3f(-29, 0, 58.0);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-25, 0, 58);
    glVertex3f(-25, 16, 58);
    glVertex3f(-29, 16, 58);
    glVertex3f(-29, 0, 58);
    glEnd();

    glBegin(GL_QUADS);//tianglogo2
    glColor3ub(47,79,79);
    glVertex3f(0, 0, 62.0);
    glVertex3f(0, 16, 62.0);
    glVertex3f(4, 16, 62.0);
    glVertex3f(4, 0, 62.0);
    glEnd();

        glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(0, 0, 62.0);
    glVertex3f(0, 16, 62.0);
    glVertex3f(0, 16, 58.0);
    glVertex3f(0, 0, 58.0);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(4, 0, 62.0);
    glVertex3f(4, 16, 62.0);
    glVertex3f(4, 16, 58.0);
    glVertex3f(4, 0, 58.0);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(0, 0, 58);
    glVertex3f(0, 16, 58);
    glVertex3f(4, 16, 58);
    glVertex3f(4, 0, 58);
    glEnd();

    //tamanLogo
    glBegin(GL_POLYGON);
    glColor3ub(0,128,0);
    glVertex3f(-30,0, 53);
    glVertex3f(-30,0, 65);
    glVertex3f(-28, 0, 67);
    glVertex3f(-24, 0,68);
    glVertex3f(-20, 0,70);
    glVertex3f(-4, 0,70);
    glVertex3f(0, 0,68);
    glVertex3f(4, 0,67);
    glVertex3f(6, 0, 65);
    glVertex3f(6, 0, 53);
    glEnd();

    //Satpambank
    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-83, -2, 111);
    glVertex3f(-83, 7, 111);
    glVertex3f(-105, 7, 111);
    glVertex3f(-105, -2, 111);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-93, -2, 93);
    glVertex3f(-93, 7, 93);
    glVertex3f(-105, 7, 93);
    glVertex3f(-105, -2, 93);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-83, -2, 111);
    glVertex3f(-83, 7, 111);
    glVertex3f(-83, 7, 93);
    glVertex3f(-83, -2, 93);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(47,79,79);
    glVertex3f(-105, -2, 111);
    glVertex3f(-105, 7, 111);
    glVertex3f(-105, 7, 93);
    glVertex3f(-105, -2, 93);
    glEnd();

    glBegin(GL_QUADS);//pintu
    glColor3ub(250,235,215);
    glVertex3f(-93, -2, 93);
    glVertex3f(-93, 20, 93);
    glVertex3f(-83, 20, 93);
    glVertex3f(-83, -2, 93);
    glEnd();

    glBegin(GL_QUADS);//pintu
    glColor3ub(139,69,19);
    glVertex3f(-92, -2, 92.9);
    glVertex3f(-92, 18, 92.9);
    glVertex3f(-84, 18, 92.9);
    glVertex3f(-84, -2, 92.9);
    glEnd();

    glBegin(GL_QUADS);//kaca
    glColor3ub(0,0,0);
    glVertex3f(-83, 5, 111);
    glVertex3f(-83, 20, 111);
    glVertex3f(-105, 20, 111);
    glVertex3f(-105, 5, 111);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(0,0,0);
    glVertex3f(-93, 7, 93);
    glVertex3f(-93, 20, 93);
    glVertex3f(-105, 20, 93);
    glVertex3f(-105, 7, 93);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(0,0,0);
    glVertex3f(-83, 7, 111);
    glVertex3f(-83, 20, 111);
    glVertex3f(-83, 20, 93);
    glVertex3f(-83, 7, 93);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(0,0,0);
    glVertex3f(-105, 7, 111);
    glVertex3f(-105, 20, 111);
    glVertex3f(-105, 20, 93);
    glVertex3f(-105, 7, 93);
    glEnd();

    //atap
    glBegin(GL_TRIANGLES);
    glColor3f(1,0.4,0);
    glVertex3f(-94,28, 102);
    glVertex3f(-82, 19, 113);
    glVertex3f(-106, 19, 113);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(1,0.4,0);
    glVertex3f(-94,28, 102);
    glVertex3f(-82, 19, 91);
    glVertex3f(-106, 19, 91);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(1,0.4,0);
    glVertex3f(-94, 28, 102);
    glVertex3f(-82, 19, 91);
    glVertex3f(-82, 19, 113);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(1,0.4,0);
    glVertex3f(-94, 28, 102);
    glVertex3f(-106, 19, 91);
    glVertex3f(-106, 19, 113);
    glEnd();

    //TiangPagarKiri
    glBegin(GL_QUADS);//1
    glColor3ub(95,158,160);
    glVertex3f(-200, -5, 120);
    glVertex3f(-200, 25, 120);
    glVertex3f(-196, 25, 120);
    glVertex3f(-196, -5, 120);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-200, -5, 116);
    glVertex3f(-200, 25, 116);
    glVertex3f(-196, 25, 116);
    glVertex3f(-196, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-200, -5, 120);
    glVertex3f(-200, 25, 120);
    glVertex3f(-200, 25, 116);
    glVertex3f(-200, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-196, -5, 120);
    glVertex3f(-196, 25, 120);
    glVertex3f(-196, 25, 116);
    glVertex3f(-196, -5, 116);
    glEnd();

      glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-200, 25, 120);
    glVertex3f(-196, 25, 120);
    glVertex3f(-196, 25, 116);
    glVertex3f(-200, 25, 116);
    glEnd();


    glBegin(GL_QUADS);//2
    glColor3ub(95,158,160);
    glVertex3f(-160, -5, 120);
    glVertex3f(-160, 25, 120);
    glVertex3f(-156, 25, 120);
    glVertex3f(-156, -5, 120);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-160, -5, 116);
    glVertex3f(-160, 25, 116);
    glVertex3f(-156, 25, 116);
    glVertex3f(-156, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-160, -5, 120);
    glVertex3f(-160, 25, 120);
    glVertex3f(-160, 25, 116);
    glVertex3f(-160, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-156, -5, 120);
    glVertex3f(-156, 25, 120);
    glVertex3f(-156, 25, 116);
    glVertex3f(-156, -5, 116);
    glEnd();

    glBegin(GL_QUADS);//3
    glColor3ub(95,158,160);
    glVertex3f(-120, -5, 120);
    glVertex3f(-120, 25, 120);
    glVertex3f(-116, 25, 120);
    glVertex3f(-116, -5, 120);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-120, -5, 116);
    glVertex3f(-120, 25, 116);
    glVertex3f(-116, 25, 116);
    glVertex3f(-116, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-120, -5, 120);
    glVertex3f(-120, 25, 120);
    glVertex3f(-120, 25, 116);
    glVertex3f(-120, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-116, -5, 120);
    glVertex3f(-116, 25, 120);
    glVertex3f(-116, 25, 116);
    glVertex3f(-116, -5, 116);
    glEnd();

    glBegin(GL_QUADS);//4
    glColor3ub(95,158,160);
    glVertex3f(-80, -5, 120);
    glVertex3f(-80, 25, 120);
    glVertex3f(-76, 25, 120);
    glVertex3f(-76, -5, 120);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-80, -5, 116);
    glVertex3f(-80, 25, 116);
    glVertex3f(-76, 25, 116);
    glVertex3f(-76, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-80, -5, 120);
    glVertex3f(-80, 25, 120);
    glVertex3f(-80, 25, 116);
    glVertex3f(-80, -5, 116);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(95,158,160);
    glVertex3f(-76, -5, 120);
    glVertex3f(-76, 25, 120);
    glVertex3f(-76, 25, 116);
    glVertex3f(-76, -5, 116);
    glEnd();


    //tembokPager
    glBegin(GL_QUADS);
    glColor3ub(245,222,179);
    glVertex3f(-200, -5, 119);
    glVertex3f(-200, 10, 119);
    glVertex3f(-76, 10, 119);
    glVertex3f(-76, -5, 119);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(245,222,179);
    glVertex3f(-200, -5, 117);
    glVertex3f(-200, 10, 117);
    glVertex3f(-76, 10, 117);
    glVertex3f(-76, -5, 117);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(245,222,179);
    glVertex3f(-200, 10, 119);
    glVertex3f(-200, 10, 117);
    glVertex3f(-76, 10, 117);
    glVertex3f(-76, 10, 119);
    glEnd();

    //jlnTro
    glBegin(GL_QUADS);
    glColor3ub(169,169,169);
    glVertex3f(-200, -2, 120);
    glVertex3f(80, -2, 120);
    glVertex3f(80, -2,170);
    glVertex3f(-200, -2, 170);
    glEnd();

    //Parkir
    glBegin(GL_POLYGON);
    glColor3ub(169,169,169);
    glVertex3f(-150, -2, 120);
    glVertex3f(-140, -2, 100);
    glVertex3f(-115, -2,80);
    glVertex3f(-70, -2, 80);
    glVertex3f(-70, -2, 120);
    glEnd();

    glBegin(GL_POLYGON);
    glColor3ub(255,255,255);//dpntro
    glVertex3f(-200, -5, 170);
    glVertex3f(-200, -2, 170);
    glVertex3f(-76, -2,170);
    glVertex3f(-74.5, -5, 170);
    glVertex3f(-74, -5, 170);
    glEnd();

    glBegin(GL_QUADS);//diffroad
    glColor3ub(255,255,0);
    glVertex3f(-200, -1.9, 155);
    glVertex3f(80, -1.9, 155);
    glVertex3f(80, -1.9,160);
    glVertex3f(-200, -1.9, 160);
    glEnd();

    //jalan
    glBegin(GL_QUADS);
    glColor3ub(105,105,105);
    glVertex3f(-200, -5, 120);
    glVertex3f(500, -5, 120);
    glVertex3f(500, -5,230);
    glVertex3f(-200, -5, 230);
    glEnd();


     glBegin(GL_QUADS);//markajalan
    glColor3ub(255,255,255);
    glVertex3f(-77, -4.8, 170);
    glVertex3f(-75, -4.8, 170);
    glVertex3f(-75, -4.8,210);
    glVertex3f(-77, -4.8, 210);
    glEnd();

    glBegin(GL_QUADS);
    glColor3ub(255,255,255);
    glVertex3f(-200, -4.8, 210);
    glVertex3f(-75, -4.8, 210);
    glVertex3f(-75, -4.8,207);
    glVertex3f(-200, -4.8, 207);
    glEnd();

    glBegin(GL_QUADS);//jlrsepeda
    glColor3ub(50,205,50);
    glVertex3f(-200, -4.8, 182);
    glVertex3f(500, -4.8, 182);
    glVertex3f(500, -4.8,185);
    glVertex3f(-200, -4.8, 185);
    glEnd();

    glBegin(GL_QUADS);//ujungpagarkanan
    glColor3f(0.5, 1.0, 1.0);
    glVertex3f(55, -2, 120);
    glVertex3f(55, 22, 120);
    glVertex3f(59, 22, 120);
    glVertex3f(59, -2, 120);
    glEnd();


    glPushMatrix();
    glPopMatrix();

    glutSwapBuffers();

}

void idle(){
    if (!mouseDown) {
        xrot += 0.3f;
        yrot += 0.4f;
    }

    glutPostRedisplay();
}

void mouse(int button, int state, int x, int y) {
    if (button == GLUT_LEFT_BUTTON && state == GLUT_DOWN) {
        mouseDown = true;
        xdiff = x - yrot;
        ydiff = -y + xrot;
    }
    else
        mouseDown = false;
}

void mouseMotion(int x, int y) {
    if (mouseDown) {
        yrot = x - xdiff;
        xrot = y + ydiff;

        glutPostRedisplay();
    }
}

void ukuran(int lebar, int tinggi)
{
    if (tinggi == 0) tinggi = 1;

    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluPerspective(40, lebar / tinggi, 5.0, 600.0);
    glTranslatef(0.0, -5.0, -350.0);
  glMatrixMode(GL_MODELVIEW);
}
