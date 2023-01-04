#include <GL/gl.h>
#include <GL/glu.h>
#include <GL/glut.h>
#include <stdlib.h>
#include <windows.h>
#include <math.h>
#include<mmsystem.h>
float cx=0,cy=0,cz=0,step;

void(timer)(int);
int zRotated=0;
float x;

//----------------------keyboard--------------------------
void keyboard(unsigned char Key,int x,int y)
    {
    if(Key=='w'){cz-=0.1;} if(Key=='s'){cz+=0.1;}//forward and back
    if(Key=='a'){cx-=0.1;} if(Key=='d'){cx+=0.1;}//left and right

    glutPostRedisplay();
    }
void timer(int)
{
    glutPostRedisplay();
    glutTimerFunc(1000/60,timer,0);

	step+=0.01 ;
	if (x<=1.5){
        x+=0.01;
	}
}
void reshapeFunc (int w, int h)
{
    glViewport(0,0,(GLsizei)w,(GLsizei)h);
    glMatrixMode(GL_PROJECTION);
    glLoadIdentity();
    gluPerspective (40.0, (GLdouble)w / (GLdouble)h, 0.5, 20.0);
    glMatrixMode(GL_MODELVIEW);
}
void snowman(){
    //snowman
    glColor3f (1, 1, 1);
    glPushMatrix ();
    glTranslatef    (-1.5+cx, -2, 1+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(1.3,10, 30);
    glPopMatrix ();

    glColor3f (1, 1, 1);
    glPushMatrix ();
    glTranslatef    (-1.5+cx, 0, 1+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(1,10, 30);
    glPopMatrix ();

    glColor3f (1, 1, 1);
    glPushMatrix ();
    glTranslatef    (-1.5+cx, 1.5, 1+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.7,10, 30);
    glPopMatrix ();
    //eye
    glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.2+cx, 1.5, 2+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.1,10, 30);
    glPopMatrix ();

    glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.7+cx, 1.5, 2+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.1,10, 30);
    glPopMatrix ();
//cone
    glColor3f (0.5, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.2+cx, 1, 4+cz);
    glRotatef       (180,0,0,0);
    glutSolidCone(0.1,1,21,5);
    glPopMatrix ();
//button
glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.3+cx, -2, 3+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.3+cx, -1.4, 3+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.3+cx, -1, 3+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.3+cx, -0.3, 3+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

     glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.3+cx, 0.1, 3+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0, 0, 0);
    glPushMatrix ();
    glTranslatef    (-1.3+cx, 0.5, 3+cz);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();
    //cone
    glBegin(GL_TRIANGLES);
    //front
      glColor3f(0.1,0.9,0.7);
      glVertex3f( -1.5f+cx, 3.1f, 1.0f+cz);
      glColor3f(0.1,0.3,0.);
      glVertex3f(-2.1f+cx, 2.1f, 1.0f+cz);
      glColor3f(0.1,0.0,0.7);
      glVertex3f(-1.0f+cx, 2.1f, 1.0f+cz);
      //back

      glVertex3f( -1.5f+cx, 3.1f, -0.5f+cz);
      glVertex3f(-2.1f+cx, 2.1f, -0.5f+cz);
      glVertex3f(-1.0f+cx, 2.1f, -0.5f+cz);
      //right

      glVertex3f( -1.5f+cx, 3.1f, 1.0f+cz);
      glVertex3f( -1.5f+cx, 3.1f, -0.5f+cz);
      glVertex3f(-1.0f+cx, 2.1f, -0.5f+cz);
      glVertex3f(-1.0f+cx, 2.1f, 1.0f+cz);
      //left

      glVertex3f( -1.5f+cx, 3.1f, 1.0f+cz);
      glVertex3f( -1.5f+cx, 3.1f, -0.5f+cz);
      glVertex3f(-2.1f+cx, 2.1f, -0.5f+cz);
      glVertex3f(-2.1f+cx, 2.1f, 1.0f+cz);
      //down

      glVertex3f(-2.1f+cx, 2.1f, 1.0f+cz);
      glVertex3f(-2.1f+cx, 2.1f, -0.5f+cz);
      glVertex3f(-1.0f+cx, 2.1f, -0.5f+cz);
      glVertex3f(-1.0f+cx, 2.1f, 1.0f+cz);

   glEnd();

    //torus
    glPushMatrix();
    glColor3f(0.5,0,0);
    glTranslatef(-1.5+cx,2,1.2+cz);
    glRotatef(-90.0,1,0,0);
    glutSolidTorus(0.1,0.5,50,50);
    glPopMatrix();
}
void cloud(){
    //cloud 1
    glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-4+step,4,0.0);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-3.5+step,4,0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.5,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-3+step,4,-0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

//cloud 2
    glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-1+step,4,0.0);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-0.5+step,4,0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.5,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(0+step,4,-0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

    //cloud 3
    glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(2+step,4,0.0);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(2.5+step,4,0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.5,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(3+step,4,-0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

    //cloud 4
    glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-7+step,4,0.0);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-6.5+step,4,0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.5,10,30);
    glPopMatrix();

     glColor3f(0.9,0.9,0.9);
    glPushMatrix();
    glTranslatef(-6+step,4,-0.1);
    glRotatef(60.0,0,1,0);
    glutSolidSphere(0.4,10,30);
    glPopMatrix();

    //end of clouds
}
void tree (){
    //tree1
    glPushMatrix();
    glColor3f(0.6,0.5,0.0);
    glTranslated(-7,-1,1.5);
    glScalef(0.3,1.4,0.1);
    glutSolidCube(2);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-7,0.1,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-7,-0.5,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-7,-1.2,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    //tree2
    glPushMatrix();
    glColor3f(0.6,0.5,0.0);
    glTranslated(-10,-1,0);
    glScalef(0.3,1.4,0.1);
    glutSolidCube(2);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-10,0.1,-0.1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-10,-0.5,-0.1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    //tree3
    glPushMatrix();
    glColor3f(0.6,0.5,0.0);
    glTranslated(-6,-1,0);
    glScalef(0.3,1.4,0.1);
    glutSolidCube(2);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-6,0.1,-0.1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-6,-0.5,-0.1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    //tree4
    glPushMatrix();
    glColor3f(0.6,0.5,0.0);
    glTranslated(-4,-1,1.5);
    glScalef(0.3,1.4,0.1);
    glutSolidCube(2);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-4,0.1,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-4,-0.5,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-4,-1.1,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.9,1.7,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

//end of tree
}
void ballsOfTree(){
    //balls on tree 4
    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-4, -0.5-x, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

     glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-4, -0.9, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.5, -0.2, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.5, -0.8, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.7, 0.5, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-4, 0, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.2, 0.7, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.2, 0.3, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.7, 1, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-3.2, -0.5, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();
//end balls on tree4
//balls on tree1

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6.7, -1-x, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6.2, -0.7, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-5.8, -1, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6.7, -0.5, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-5.8, -0.5, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-5.8, 0, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6.7, 0, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6, -0.2, 3.5);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-5.8, 0.5, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6.7, 0.5, 3);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6, 0.2, 3.5);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();

    glColor3f (0.6, 0, 0);
    glPushMatrix ();
    glTranslatef    (-6, 0.7, 3.5);
    glRotatef       (60.0, 1,0,0);
    glutSolidSphere(0.119,10, 30);
    glPopMatrix ();







}
void grass(){

//grass tree 4
glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.6,-2.5,1.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.6,-2.5,1.5);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.4,-2.5,2.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.4,-2.5,2.5);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.6,-2.3,2.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.6,-2.3,2.5);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.7,-2.3,2.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.7,-2.3,2.5);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.7,-2.4,2.5);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-3.7,-2.4,2.5);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    //grass tree 1
    glPushMatrix();
    glTranslatef(-6.7,-2.5,2);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-6.7,-2.5,2);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-6.4,-2.5,2);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-6.4,-2.5,2);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-6.5,-2.4,2);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-6.5,-2.4,2);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glPushMatrix();
    glTranslatef(-6.8,-2.4,2);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(0.1,0.4,0.0);
    glPushMatrix();
    glTranslatef(-6.8,-2.4,2);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();


    //end grass
}
void stars(){
    //stars
    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-4,4.5,-1.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glColor3f(0.9,0.9,0.9);
    glutWireCone(0.1,0.5,5,5);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-4,4.5,-1.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-4,4.5,-1.5);
    glRotatef(zRotated,0,1,0);
    glRotatef(-20.0,0,0,1);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-4,4.5,-1.5);
    glRotatef(zRotated,0,1,0);
    glRotatef(190.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();
//star2
    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-6,5,-1.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-6,5,-1.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-6,5,-1.5);
    glRotatef(zRotated,0,1,0);
    glRotatef(-20.0,0,0,1);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(-6,5,-1.5);
    glRotatef(zRotated,0,1,0);
    glRotatef(190.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();
        glPopMatrix();
//star3
   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(2.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(2.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(2.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(2.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();
    //star4
   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(4,5,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(4,5,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(4,5,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(4,5,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();
    //star5
   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(6.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

    glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(6.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,1,0,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(6.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();

   glColor3f(1.0,1.0,1.0);
    glPushMatrix();
    glTranslatef(6.5,4.3,-0.5);
    glRotatef(zRotated,0,0,1);
    glRotatef(-90.0,0,1,0);
    glutSolidCone(0.1,0.5,21,10);
    glScalef(0,0,0.1);
    glPopMatrix();
//end star
}
void house(){

//house
glPushMatrix();
    glColor3f(0.6,0.3,0.0);
    glTranslated(4,0,-1);
    glScalef(6,3,-1.3);
    glutSolidCube(1.5);
    glPopMatrix();
    //window1 right1
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(7,1.2,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window2
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(7,-0.1,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window3
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(7,-1.4,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window1 left1
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(5.5,1.2,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window2
    glPushMatrix();
   glColor3f(0.6,0.5,0.4);
    glTranslated(5.5,-0.1,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window3
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(5.5,-1.4,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //right2
    glPushMatrix();
   glColor3f(0.6,0.5,0.4);
    glTranslated(2,1.2,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window2
    glPushMatrix();
   glColor3f(0.6,0.5,0.4);
    glTranslated(2,-0.1,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window3
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(2,-1.4,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //left2
    glPushMatrix();
    glColor3f(0.6,0.5,0.4);
    glTranslated(0.5,1.2,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window2
    glPushMatrix();
   glColor3f(0.6,0.5,0.4);
    glTranslated(0.5,-0.1,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //window3
    glPushMatrix();
   glColor3f(0.6,0.5,0.4);
    glTranslated(0.5,-1.4,-1);
    glScalef(2.3,2,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //door
    glPushMatrix();
    glColor3f(0.6,0.6,0.5);
    glTranslated(3.7,-1,-1);
    glScalef(2.5,5,0);
    glutSolidCube(0.5);
    glPopMatrix();
    //torus
    glPushMatrix();
    glColor3f(0.6,0.4,0);
    glTranslatef(3.9,-1,-0.5);
    glRotatef(180.0,1,0,0);
    glutSolidTorus(0.1,0.1,40,40);
    glPopMatrix();

}
void box(){
    glBegin(GL_QUADS);
      // Front
      glColor3f(0.8,0.4,0.0);
      glVertex3f( -3.5f, -1.5f, 1.5f);
      glColor3f(0.8,0.4,0.1);
      glVertex3f(-3.5f, -2.5f, 1.5f);
      glColor3f(0.8,0.5,0.1);
      glVertex3f(-2.5f, -2.5f, 1.5f);
      glColor3f(0.7,0.5,0.1);
      glVertex3f(-2.5f, -1.5f, 1.5f);
        //back
    glColor3f(0.8,0.8,0.0);
     glVertex3f( -3.5f, -1.5f, -1.5f);
     glVertex3f(-3.5f, -2.5f, -1.5f);
     glVertex3f(-2.5f, -2.5f, -1.5f);
     glVertex3f(-2.5f, -1.5f, -1.5f);
     //UP
    glColor3f(0.5,0.3,0.0);
     glVertex3f(-2.5f, -1.5f, 1.5f);
     glVertex3f(-2.5f, -1.5f, -1.5f);
     glVertex3f( -3.5f, -1.5f, -1.5f);
     glVertex3f( -3.5f, -1.5f, 1.5f);
      //right
      glColor3f(0.5,0.0,0.0);
     glVertex3f(-2.5f, -1.5f, 1.5f);
     glVertex3f(-2.5f, -1.5f, -1.5f);
     glVertex3f(-2.5f, -2.5f, -1.5f);
     glVertex3f(-2.5f, -2.5f, 1.5f);
     //left
      glColor3f(0.5,0.0,0.0);
     glVertex3f( -3.5f, -1.5f, 1.5f);
     glVertex3f( -3.5f, -1.5f, -1.5f);
     glVertex3f(-3.5f, -2.5f, -1.5f);
     glVertex3f(-3.5f, -2.5f, 1.5f);
     //DOWN
     glColor3f(0.5,0.0,0.0);
     glVertex3f(-2.5f, -2.5f, 1.5f);
     glVertex3f(-2.5f, -2.5f, -1.5f);
     glVertex3f(-3.5f, -2.5f, -1.5f);
     glVertex3f(-3.5f, -2.5f, 1.5f);
   glEnd();
}
void moon(){
    glColor3f (1, 1, 1);
    glPushMatrix ();
    glTranslatef    (-8, 4, 1);
    glRotatef       (60.0, 1,1,0);
    glutSolidSphere(0.6,10, 30);
    glPopMatrix ();

}
void background(){
    glPushMatrix();
    glColor3f(0.0,0.0,0.2);
    glTranslated(0,5,-4);
    glScalef(11,5,0);
    glutSolidCube(3);
    glPopMatrix();

     glPushMatrix();
    glColor3f(0.7,0.7,0.7);
    glTranslated(0,-5,-4);
    glScalef(11,5,0);
    glutSolidCube(3);
    glPopMatrix();



}
void display (void)
{
    glClear (GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
    glLoadIdentity ();
    glTranslatef (0.0, 0.0, -15.0);
cloud();
tree();
ballsOfTree();
grass();
snowman();
stars();
house();
box();
moon();
background();





















    glutSwapBuffers();
}


void idleFunc (void)
{
    zRotated += 1;
    glutPostRedisplay();
}

void texture (void){

const GLfloat light_ambient[]  = { 0.0f, 0.0f, 0.0f, 1.0f };
const GLfloat light_diffuse[]  = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat light_specular[] = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat light_position[] = { 2.0f, 5.0f, 5.0f, 0.0f };

const GLfloat mat_ambient[]    = { 0.7f, 0.7f, 0.7f, 1.0f };
const GLfloat mat_diffuse[]    = { 0.8f, 0.8f, 0.8f, 1.0f };
const GLfloat mat_specular[]   = { 1.0f, 1.0f, 1.0f, 1.0f };
const GLfloat high_shininess[] = { 100.0f };

    glEnable(GL_CULL_FACE);
    glCullFace(GL_BACK);

    glEnable(GL_DEPTH_TEST);
    glDepthFunc(GL_LESS);

    glEnable(GL_LIGHT0);
    glEnable(GL_NORMALIZE);
    glEnable(GL_COLOR_MATERIAL);
    glEnable(GL_LIGHTING);

    glLightfv(GL_LIGHT0, GL_AMBIENT,  light_ambient);
    glLightfv(GL_LIGHT0, GL_DIFFUSE,  light_diffuse);
    glLightfv(GL_LIGHT0, GL_SPECULAR, light_specular);
    glLightfv(GL_LIGHT0, GL_POSITION, light_position);

    glMaterialfv(GL_FRONT, GL_AMBIENT,   mat_ambient);
    glMaterialfv(GL_FRONT, GL_DIFFUSE,   mat_diffuse);
    glMaterialfv(GL_FRONT, GL_SPECULAR,  mat_specular);
    glMaterialfv(GL_FRONT, GL_SHININESS, high_shininess);


}

//----------------------------------  main  ------------------------------------

int main (int argc, char **argv)
{
    glutInit               (&argc, argv);
    glutInitDisplayMode(GLUT_RGB | GLUT_DOUBLE | GLUT_DEPTH);
    glutInitWindowSize     (800, 700);
    glutInitWindowPosition (700, 200);
    glutCreateWindow       ("20100755");



    glutDisplayFunc (display);
    glutReshapeFunc (reshapeFunc);
    glutIdleFunc    (idleFunc);
    //sndPlaySound("audio.wav",SND_ALIAS);
    glutTimerFunc(0,timer,0);
    glutKeyboardFunc(keyboard);
    glClearColor(0,0,0,0);
    texture();


    glutMainLoop();
}

