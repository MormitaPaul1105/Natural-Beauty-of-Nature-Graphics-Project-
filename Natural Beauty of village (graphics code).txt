#include <windows.h>  // for MS Windows
#include<cstdio>
#include <GL/gl.h>
#include <GL/glut.h>
#define PI 3.141516
#include<math.h>
#include<iostream>

using namespace std;


GLfloat position_sun = 0.0f;
GLfloat position_sun_down = 0.0f;
GLfloat speed_sun = 0.006f;

GLfloat position_moon = 0.0f;
GLfloat position_moon_down = 0.0f;
GLfloat speed_moon = 0.0075;

bool rainday=false;
bool flower= false;
GLfloat position1 = 0.0f;
GLfloat position2 = 0.0f;
GLfloat position3 = 0.0f;
GLfloat position4 = 0.0f;
GLfloat position5 = 0.0f;
GLfloat position6 = 0.0f;
GLfloat position_3rd_car = 0.0f;
GLfloat position8 = 0.0f;
GLfloat position_rain = 0.0f;
GLfloat position_snow = 0.0f;


GLfloat speed1 = 0.01f;
GLfloat speed2 = 0.02f;
GLfloat speed_snow = 0.017f;
GLfloat speed3 = 0.03f;
GLfloat speed4 = 0.03f;
GLfloat speed5 = 0.025f;
GLfloat speed6 = 0.017f;
GLfloat speed_3rd_car = 0.02f;
GLfloat speed8 = 0.003f;
GLfloat speed_rain = 1.0f;

void load_Start();
void load_DayBack();


void Idle()
{
    glutPostRedisplay();
}

void update_sun(int value)
{

    if(position_sun <-1.0)
    {
        position_sun = 1.0f;
        position_sun_down = 1.0f;
    }
    position_sun -= speed_sun;
    position_sun_down -= speed_sun/3;

	glutTimerFunc(135, update_sun, 0);
}


void update_moon(int value)
{
    if(position_moon <-1.0)
    {
        position_moon = 1.0f;
        position_moon_down = 1.0f;
    }
    position_moon -= speed_moon;
    position_moon_down -= speed_moon/3;

	glutTimerFunc(80, update_moon, 0);
}

void update1(int value) {

    if(position1 <-1.0)
        position1 = 1.0f;

    position1 -= speed1;

glutPostRedisplay();
glutTimerFunc(100, update1, 0);
}






void update2(int value) {

    if(position2 <-1.0)
        position2 = 1.0f;

    position2 -= speed2;

glutPostRedisplay();
glutTimerFunc(100, update2, 0);
}



void update3(int value) {

    if(position3 <-1.0)
        position3 = 1.0f;

    position3 -= speed3;

glutPostRedisplay();
glutTimerFunc(100, update3, 0);
}


void update4(int value) {

    if(position4 <-1.0)
        position4 = 1.0f;

    position4 -= speed4;

glutPostRedisplay();
glutTimerFunc(100, update4, 0);
}

void update5(int value) {

    if(position5 <-1.0)
        position5 = 1.0f;

    position5 -= speed5;

glutPostRedisplay();
glutTimerFunc(100, update5, 0);
}
void update6(int value) {

    if(position6 <-1.0)
        position6 = 1.0f;

    position6 -= speed6;

glutPostRedisplay();
glutTimerFunc(100, update6, 0);
}
void update_3rd_car(int value) {

    if(position_3rd_car <-1.0)
        position_3rd_car = 1.0f;

 position_3rd_car -= speed_3rd_car;

glutPostRedisplay();
glutTimerFunc(100, update_3rd_car, 0);
}

void update8(int value) {

    if(position8 <-1.0)
        position8 = 1.0f;

    position8 -= speed8;

glutPostRedisplay();
glutTimerFunc(100, update8, 0);
}
void update_rain(int value) {

    if(position_rain <-1.0)
        position_rain = 1.0f;

    position_rain -= speed_rain;

glutPostRedisplay();
glutTimerFunc(0, update_rain, 0);
}

void update_snow(int value) {

    if(position_snow <-1.0)
        position_snow = 1.0f;

    position_snow -= speed_snow;

glutPostRedisplay();
glutTimerFunc(0, update_snow, 0);
}
void Rainy_Sky(){
if(rainday==true)
    {
        //sky
	glBegin(GL_QUADS);
	glColor3f(0.6f, 0.7f, 0.7f);
	glVertex2f(-1.0f, 1.0f);
	glVertex2f(-1.0f, 0.45f);

	glVertex2f(1.0f, 0.45f);
	glVertex2f(1.0f, 1.0f);
	 glEnd();
    }
}

//sky
void Rainy_Night_Sky(){
if(rainday==true)
    {
	glBegin(GL_QUADS);
	glColor3f(0.0f, 0.0f, 0.20f);

	glVertex2f(-1.0f, 1.0f);
	glVertex2f(-1.0f, 0.45f);

	glVertex2f(1.0f, 0.45f);
	glVertex2f(1.0f, 1.0f);
	 glEnd();
    }
}

void Day_sky() {

	//sky
	glBegin(GL_QUADS);
	glColor3f(0.75f, 1.0f, 1.0f);

	glVertex2f(-1.0f, 1.0f);
	glVertex2f(-1.0f, 0.45f);

	glVertex2f(1.0f, 0.45f);
	glVertex2f(1.0f, 1.0f);
	 glEnd();



glLoadIdentity();


}
void Evening_sky() {

	//sky
	glBegin(GL_QUADS);
	glColor3f(1.0f, 0.50f, 0.0f);

	glVertex2f(-1.0f, 1.0f);
	glVertex2f(-1.0f, 0.45f);

	glVertex2f(1.0f, 0.45f);
	glVertex2f(1.0f, 1.0f);
	 glEnd();

glLoadIdentity();

}

void Night_sky() {

	//sky
	glBegin(GL_QUADS);
	glColor3f(0.0f, 0.0f, 0.40f);

	glVertex2f(-1.0f, 1.0f);
	glVertex2f(-1.0f, 0.45f);

	glVertex2f(1.0f, 0.45f);
	glVertex2f(1.0f, 1.0f);
	 glEnd();

glLoadIdentity();


}



//Sun
void Sun(){
glPushMatrix();
glTranslatef(0.0f, position_sun,0.0f);
int k;

GLfloat d1=0.7f;
GLfloat d2= 0.85f;
GLfloat r7 = 0.12f;
int triangle7=50;



GLfloat tp7 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 0.0f);
glVertex2f (d1,d2);
for(k= 0;k<=triangle7; k++)
{
glVertex2f (
d1+(r7*cos(k*tp7/triangle7)),
d2+(r7*sin(k*tp7/triangle7))
);
}
glEnd ();
glPopMatrix();
glLoadIdentity();
}

//Moon
void Moon(){
glPushMatrix();
glTranslatef(0.0f, position_moon,0.0f);
int k;

GLfloat z1=0.7f;
GLfloat z2= 0.85f;
GLfloat r100 = 0.12f;
int triangle100=50;



GLfloat tp100 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.9f, 1.0f, 1.0f);
glVertex2f (z1,z2);
for(k= 0;k<=triangle100; k++)
{
glVertex2f (
z1+(r100*cos(k*tp100/triangle100)),
z2+(r100*sin(k*tp100/triangle100))
);
}
glEnd ();
glPopMatrix();
glLoadIdentity();

}



      //River
void Day_river(){
      glBegin(GL_POLYGON);
      glColor3f(0.0f, 0.50f, 1.0f);
      glVertex2f(-1.0f, 0.45f);
      glVertex2f(-1.0f, 0.1f);

      glVertex2f( 0.2f,  0.1f);
      glVertex2f( 0.3f,  0.0f);
      glVertex2f( 0.2f,  -0.1f);
      glVertex2f( 0.4f,  -0.3f);

      glVertex2f( 0.1f,  -0.3f);
      glVertex2f( 0.3f,  -0.5f);


      glVertex2f( 0.0f,  -0.5f);
      glVertex2f( 0.5f,  -0.7f);


      glVertex2f(-1.0f, -0.7f);
      glVertex2f(-1.0f, -1.0f);

      glVertex2f(1.0f, -1.0f);
      glVertex2f(1.0f, 0.45f);

      glEnd();
      glLoadIdentity();
}
void Night_river(){
      glBegin(GL_POLYGON);
      glColor3f(0.0f, 0.30f, 1.0f);
      glVertex2f(-1.0f, 0.45f);
      glVertex2f(-1.0f, 0.1f);

      glVertex2f( 0.2f,  0.1f);
      glVertex2f( 0.3f,  0.0f);
      glVertex2f( 0.2f,  -0.1f);
      glVertex2f( 0.4f,  -0.3f);

      glVertex2f( 0.1f,  -0.3f);
      glVertex2f( 0.3f,  -0.5f);


      glVertex2f( 0.0f,  -0.5f);
      glVertex2f( 0.5f,  -0.7f);


      glVertex2f(-1.0f, -0.7f);
      glVertex2f(-1.0f, -1.0f);

      glVertex2f(1.0f, -1.0f);
      glVertex2f(1.0f, 0.45f);

      glEnd();
      glLoadIdentity();
}



//road
void Day_road(){
	glBegin(GL_QUADS);
	glColor3f(0.56f, 0.46f, 0.27f);

	glVertex2f(-1.0f, 0.45f);
	glVertex2f(-1.0f, 0.1f);

	glVertex2f(1.0f, 0.1f);
	glVertex2f(1.0f, 0.45f);
	 glEnd();
	 glLoadIdentity();

}

void Night_road(){
	glBegin(GL_QUADS);
	glColor3f(0.36f, 0.26f, 0.07f);

	glVertex2f(-1.0f, 0.45f);
	glVertex2f(-1.0f, 0.1f);

	glVertex2f(1.0f, 0.1f);
	glVertex2f(1.0f, 0.45f);
	 glEnd();
	 glLoadIdentity();

}


//Grass
void Day_grass(){
	  glBegin(GL_POLYGON);
      glColor3f(0.0f, 1.0f, 0.0f);
      glVertex2f(-1.0f, 0.1f);
      glVertex2f( -1.0f, -0.7f);

      glVertex2f( 0.1f, -0.7f);

      glVertex2f( 0.5f,  -0.7f);
      glVertex2f( 0.0f,  -0.5f);

      glVertex2f( 0.3f,  -0.5f);
      glVertex2f( 0.1f,  -0.3f);

      glVertex2f( 0.4f,  -0.3f);
      glVertex2f( 0.2f,  -0.1f);
      glVertex2f( 0.3f,  0.0f);
      glVertex2f( 0.2f,  0.1f);
      glEnd();





	glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(-1.0f, -0.7f);
    glVertex2f(-1.0f, -0.73f);
    glVertex2f(0.5f, -0.73f);
    glVertex2f(0.5f, -0.7f);
glEnd();


glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.1f, -0.5f);
    glVertex2f(0.16f, -0.52f);
    glVertex2f(0.3f, -0.52f);
    glVertex2f(0.3f, -0.5f);
glEnd();



glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.12f, -0.32f);
    glVertex2f(0.4f, -0.32f);
    glVertex2f(0.4f, -0.3f);
glEnd();


glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.2f, -0.1f);
    glVertex2f(0.21f, -0.112f);
    glVertex2f(0.3f, -0.02f);
    glVertex2f(0.3f, 0.0f);
glEnd();


glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.2f, 0.1f);
    glVertex2f(0.24f, 0.07f);
    glVertex2f(1.0f, 0.07f);
    glVertex2f(1.0f, 0.1f);
glEnd();
glLoadIdentity();

}

//Grass
void Night_grass(){
	  glBegin(GL_POLYGON);
      glColor3f(0.0f, 0.60f, 0.0f);
      glVertex2f(-1.0f, 0.1f);
      glVertex2f( -1.0f, -0.7f);

      glVertex2f( 0.1f, -0.7f);

      glVertex2f( 0.5f,  -0.7f);
      glVertex2f( 0.0f,  -0.5f);

      glVertex2f( 0.3f,  -0.5f);
      glVertex2f( 0.1f,  -0.3f);

      glVertex2f( 0.4f,  -0.3f);
      glVertex2f( 0.2f,  -0.1f);
      glVertex2f( 0.3f,  0.0f);
      glVertex2f( 0.2f,  0.1f);
      glEnd();





	glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(-1.0f, -0.7f);
    glVertex2f(-1.0f, -0.73f);
    glVertex2f(0.5f, -0.73f);
    glVertex2f(0.5f, -0.7f);
glEnd();


glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.1f, -0.5f);
    glVertex2f(0.16f, -0.52f);
    glVertex2f(0.3f, -0.52f);
    glVertex2f(0.3f, -0.5f);
glEnd();



glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.1f, -0.3f);
    glVertex2f(0.12f, -0.32f);
    glVertex2f(0.4f, -0.32f);
    glVertex2f(0.4f, -0.3f);
glEnd();


glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.2f, -0.1f);
    glVertex2f(0.21f, -0.112f);
    glVertex2f(0.3f, -0.02f);
    glVertex2f(0.3f, 0.0f);
glEnd();


glBegin(GL_QUADS);
	glColor3f(0.3f, 0.0f, 0.0f);

    glVertex2f(0.2f, 0.1f);
    glVertex2f(0.24f, 0.07f);
    glVertex2f(1.0f, 0.07f);
    glVertex2f(1.0f, 0.1f);
glEnd();
glLoadIdentity();

}

// rainy clouds
void Rainy_Clouds(){
if(rainday==true)
    {
int i;

GLfloat p1=0.2f;
GLfloat q1= 0.8f;
GLfloat r1 = 0.1f;
int triangle1=50;



GLfloat tp1 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.2f, 0.3f, 0.3f);
glVertex2f (p1,q1);
for(i= 0;i<=triangle1; i++)
{
glVertex2f (
p1+(r1*cos(i*tp1/triangle1)),
q1+(r1*sin(i*tp1/triangle1))
);
}
glEnd ();

GLfloat p2=0.1f;
GLfloat q2= 0.8f;
GLfloat r2 = 0.08f;
int triangle2=50;

GLfloat tp2 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(0.2f, 0.3f, 0.3f);
glVertex2f (p2,q2);
for(i= 0;i<=triangle2; i++)
{
glVertex2f (
p2+(r2*cos(i*tp2/triangle2)),
q2+(r2*sin(i*tp2/triangle2))
);
}
glEnd ();

GLfloat p3=0.3f;
GLfloat q3= 0.8f;
GLfloat r3 = 0.08f;
int triangle3=50;

GLfloat tp3 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(0.2f, 0.3f, 0.3f);
glVertex2f (p3,q3);
for(i= 0;i<=triangle3; i++)
{
glVertex2f (
p3+(r3*cos(i*tp3/triangle3)),
q3+(r3*sin(i*tp3/triangle3))
);
}
glEnd ();





int j;

GLfloat a1=-0.2f;
GLfloat a2= 0.8f;
GLfloat r4 = 0.1f;
int triangle4=50;



GLfloat tp4 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.2f, 0.3f, 0.3f);
glVertex2f (a1,a2);
for(j= 0;j<=triangle4; j++)
{
glVertex2f (
a1+(r4*cos(j*tp4/triangle4)),
a2+(r4*sin(j*tp4/triangle4))
);
}
glEnd ();

GLfloat b1=-0.3f;
GLfloat b2= 0.8f;
GLfloat r5 = 0.08f;
int triangle5=50;

GLfloat tp5 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(0.2f, 0.3f, 0.3f);
glVertex2f (b1,b2);
for(j= 0;j<=triangle5; j++)
{
glVertex2f (
b1+(r5*cos(j*tp5/triangle5)),
b2+(r5*sin(j*tp5/triangle5))
);
}
glEnd ();

GLfloat c1=-0.1f;
GLfloat c2= 0.8f;
GLfloat r6 = 0.08f;
int triangle6=50;

GLfloat tp6 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(0.2f, 0.3f, 0.3f);
glVertex2f (c1,c2);
for(j= 0;j<=triangle6; j++)
{
glVertex2f (
c1+(r6*cos(j*tp6/triangle6)),
c2+(r6*sin(j*tp6/triangle6))
);
}
glEnd ();
}

}








      //clouds 1
      void Clouds_1(){
glPushMatrix();
glTranslatef(-position1, 0.0f,0.0f);
int i;

GLfloat p1=0.2f;
GLfloat q1= 0.8f;
GLfloat r1 = 0.1f;
int triangle1=50;



GLfloat tp1 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (p1,q1);
for(i= 0;i<=triangle1; i++)
{
glVertex2f (
p1+(r1*cos(i*tp1/triangle1)),
q1+(r1*sin(i*tp1/triangle1))
);
}
glEnd ();

GLfloat p2=0.1f;
GLfloat q2= 0.8f;
GLfloat r2 = 0.08f;
int triangle2=50;

GLfloat tp2 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (p2,q2);
for(i= 0;i<=triangle2; i++)
{
glVertex2f (
p2+(r2*cos(i*tp2/triangle2)),
q2+(r2*sin(i*tp2/triangle2))
);
}
glEnd ();

GLfloat p3=0.3f;
GLfloat q3= 0.8f;
GLfloat r3 = 0.08f;
int triangle3=50;

GLfloat tp3 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (p3,q3);
for(i= 0;i<=triangle3; i++)
{
glVertex2f (
p3+(r3*cos(i*tp3/triangle3)),
q3+(r3*sin(i*tp3/triangle3))
);
}
glEnd ();
glPopMatrix();
glLoadIdentity();
      }

//cloud 2
void Clouds_2(){
glPushMatrix();
glTranslatef(-position2, 0.0f,0.0f);

int j;

GLfloat a1=-0.3f;
GLfloat a2= 0.9f;
GLfloat r4 = 0.08f;
int triangle4=50;



GLfloat tp4 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (a1,a2);
for(j= 0;j<=triangle4; j++)
{
glVertex2f (
a1+(r4*cos(j*tp4/triangle4)),
a2+(r4*sin(j*tp4/triangle4))
);
}
glEnd ();

GLfloat b1=-0.4f;
GLfloat b2= 0.9f;
GLfloat r5 = 0.08f;
int triangle5=50;

GLfloat tp5 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (b1,b2);
for(j= 0;j<=triangle5; j++)
{
glVertex2f (
b1+(r5*cos(j*tp5/triangle5)),
b2+(r5*sin(j*tp5/triangle5))
);
}
glEnd ();

GLfloat c1=-0.5f;
GLfloat c2= 0.9f;
GLfloat r6 = 0.08f;
int triangle6=50;

GLfloat tp6 =2.0f * PI ;

glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (c1,c2);
for(j= 0;j<=triangle6; j++)
{
glVertex2f (
c1+(r6*cos(j*tp6/triangle6)),
c2+(r6*sin(j*tp6/triangle6))
);
}
glEnd ();
glPopMatrix();
glLoadIdentity();
}


//Bird1
void Bird_1(){


glPushMatrix();
glTranslatef(-position3, 0.0f,0.0f);

       int t;

	GLfloat mm=0.182f; GLfloat nn=.801f; GLfloat radiusmm =.01f;
	int triangleAmount = 20;
	GLfloat twicePi = 2.0f * PI;

	glBegin(GL_TRIANGLE_FAN);
	    glColor3f(0.0f, 0.0f, 1.0f);
		glVertex2f(mm, nn); // center of circle
		for(t = 0; t<= triangleAmount;t++) {
			glVertex2f(
		            mm + (radiusmm * cos(t *  twicePi / triangleAmount)),
			    nn + (radiusmm * sin(t * twicePi / triangleAmount))
			);
		}
	glEnd();
    glBegin(GL_POLYGON);
    glColor3f(0.0f, 0.0f, 1.0f );
    glVertex2f(0.1f,0.8f);
    glVertex2f(0.11f,0.79f);
    glVertex2f(0.12f,0.78f);
    glVertex2f(0.16f,0.77f);
    glVertex2f(0.19f,0.79f);
    glVertex2f(0.201f,0.8f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.0f, 0.0f, 1.0f);
    glVertex2f(0.175f,0.8f);
    glVertex2f(0.15f,0.8f);
    glVertex2f(0.14f,0.84f);
    glEnd();


    glBegin(GL_TRIANGLES);
    glColor3f(0.0f, 0.0f, 1.0f );
    glVertex2f(0.175f,0.8f);
    glVertex2f(0.144f,0.8f);
    glVertex2f(0.12f,0.83f);
    glEnd();


	/////2nd bird////


	glBegin(GL_POLYGON);
    glColor3f(0.0f, 0.0f, 1.0f );
    glVertex2f(-0.02f,0.8f);
    glVertex2f(-0.01f,0.79f);
    glVertex2f(0.0f,0.78f);
    glVertex2f(0.04f,0.77f);
    glVertex2f(0.07f,0.79f);
    glVertex2f(0.081f,0.8f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(0.0f, 0.0f, 1.0f);
    glVertex2f(0.055f,0.8f);
    glVertex2f(0.03f,0.8f);
    glVertex2f(0.02f,0.84f);
    glEnd();


    glBegin(GL_TRIANGLES);
    glColor3f(0.0f, 0.0f, 1.0f );
    glVertex2f(0.055f,0.8f);
    glVertex2f(0.024f,0.8f);
    glVertex2f(0.0f,0.83f);
    glEnd();

    int i;
	GLfloat mmm=0.062f; GLfloat nnn=.801f; GLfloat radiusmmm =.01f;

	glBegin(GL_TRIANGLE_FAN);
	    glColor3f(0.0f, 0.0f, 1.0f);
		glVertex2f(mmm, nnn); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            mmm + (radiusmmm * cos(i *  twicePi / triangleAmount)),
			    nnn + (radiusmmm * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();

	glPopMatrix();
	glLoadIdentity();
}


	/////3rd bird/////
	void Bird_3(){
glPushMatrix();
glTranslatef(-position4, 0.0f,0.0f);
	glBegin(GL_POLYGON);
    glColor3f(1.0f, 0.80f, 1.0f);
    glVertex2f(-0.72f,0.8f);
    glVertex2f(-0.71f,0.79f);
    glVertex2f(-0.7f,0.78f);
    glVertex2f(-0.66f,0.77f);
    glVertex2f(-0.63f,0.79f);
    glVertex2f(-0.619f,0.8f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(1.0f, 0.80f, 1.0f);
    glVertex2f(-0.645f,0.8f);
    glVertex2f(-0.67f,0.8f);
    glVertex2f(-0.68f,0.84f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(1.0f, 0.80f, 1.0f );
    glVertex2f(-0.645f,0.8f);
    glVertex2f(-0.676f,0.8f);
    glVertex2f(-0.7f,0.83f);
    glEnd();

    int i;
	GLfloat mmmm=-0.638f; GLfloat nnnn=.801f;GLfloat radiusmmm =.01f;
int triangleAmount = 20;
GLfloat twicePi = 2.0f * PI;

	glBegin(GL_TRIANGLE_FAN);
	    glColor3f(1.0f, 0.80f, 1.0f);
		glVertex2f(mmmm,nnnn); // center of circle
		for(int i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            mmmm + (radiusmmm * cos(i *  twicePi / triangleAmount)),
			    nnnn + (radiusmmm * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();
	////4th bird////
	GLfloat mmmmm=-0.518f; GLfloat nnnnn=.801f;GLfloat radiusmm =.01f;

	glBegin(GL_TRIANGLE_FAN);
	    glColor3f(1.0f, 0.80f, 1.0f);
		glVertex2f(mmmmm, nnnnn); // center of circle
		for(i = 0; i <= triangleAmount;i++) {
			glVertex2f(
		            mmmmm + (radiusmm * cos(i *  twicePi / triangleAmount)),
			    nnnnn + (radiusmm * sin(i * twicePi / triangleAmount))
			);
		}
	glEnd();
    glBegin(GL_POLYGON);
    glColor3f(1.0f, 0.80f, 1.0f );
    glVertex2f(-0.6f,0.8f);
    glVertex2f(-0.59f,0.79f);
    glVertex2f(-0.58f,0.78f);
    glVertex2f(-0.54f,0.77f);
    glVertex2f(-0.51f,0.79f);
    glVertex2f(-0.499f,0.8f);
    glEnd();

    glBegin(GL_TRIANGLES);
    glColor3f(1.0f, 0.80f, 1.0f);
    glVertex2f(-0.525f,0.8f);
    glVertex2f(-0.55f,0.8f);
    glVertex2f(-0.56f,0.84f);
    glEnd();


    glBegin(GL_TRIANGLES);
    glColor3f(1.0f, 0.80f, 1.0f );
    glVertex2f(-0.525f,0.8f);
    glVertex2f(-0.556f,0.8f);
    glVertex2f(-0.58f,0.83f);
    glEnd();
glPopMatrix();
glLoadIdentity();
	}



//Hill
void Day_hill(){
 glBegin(GL_TRIANGLES);
	glColor3f(0.4f, 0.5f, 0.5f);
	glVertex2f(-0.80f, 0.60f);
	glVertex2f(-1.0f, 0.45f);
	glVertex2f(-0.60f, 0.45f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.4f, 0.5f, 0.5f);

	glVertex2f(-0.40f, 0.60f);
	glVertex2f(-0.60f, 0.45f);

	glVertex2f(-0.20f, 0.45f);

	 glEnd();



	 	 glBegin(GL_TRIANGLES);
	glColor3f(0.4f, 0.5f, 0.5f);

	glVertex2f(0.00f, 0.60f);
	glVertex2f(-0.20f, 0.45f);

	glVertex2f(0.20f, 0.45f);

	 glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.4f, 0.5f, 0.5f);

	glVertex2f(0.40f, 0.60f);
	glVertex2f(0.20f, 0.45f);

	glVertex2f(0.60f, 0.45f);

	 glEnd();


	  glBegin(GL_TRIANGLES);
	glColor3f(0.4f, 0.5f, 0.5f);

	glVertex2f(0.80f, 0.60f);
	glVertex2f(0.60f, 0.45f);

	glVertex2f(1.0f, 0.45f);

	 glEnd();
	 glLoadIdentity();
}



	// Fear tree 1
	void Day_fear_tree_1(){
	 glLineWidth(12);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(-0.6f, 0.5f);
	glVertex2f(-0.6f, 0.45f);
glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.60f, 0.53f);
	glVertex2f(-0.70f, 0.5f);

	glVertex2f(-0.50f, 0.5f);

	 glEnd();




	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.60f, 0.55f);
	glVertex2f(-0.67f, 0.52f);

	glVertex2f(-0.53f, 0.52f);

	 glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.60f, 0.57f);
	glVertex2f(-0.64f, 0.54f);

	glVertex2f(-0.56f, 0.54f);

	 glEnd();
	 glLoadIdentity();
	}






	// Fear tree 2
	void Day_fear_tree_2(){
	 glLineWidth(12);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(-0.2f, 0.5f);
	glVertex2f(-0.2f, 0.45f);
glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.20f, 0.54f);
	glVertex2f(-0.25f, 0.5f);
	glVertex2f(-0.15f, 0.5f);

	 glEnd();




	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.20f, 0.57f);
	glVertex2f(-0.25f, 0.52f);

	glVertex2f(-0.15f, 0.52f);

	 glEnd();


	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.20f, 0.59f);
	glVertex2f(-0.25f, 0.54f);

	glVertex2f(-0.15f, 0.54f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.20f, 0.64f);
	glVertex2f(-0.25f, 0.56f);

	glVertex2f(-0.15f, 0.56f);

	 glEnd();
	 glLoadIdentity();
	}






	 // Fear tree 3
	 void Day_fear_tree_3(){
	 glLineWidth(12);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(0.2f, 0.5f);
	glVertex2f(0.2f, 0.45f);
glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.20f, 0.53f);
	glVertex2f(0.10f, 0.5f);

	glVertex2f(0.30f, 0.5f);

	 glEnd();




	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.20f, 0.55f);
	glVertex2f(0.13f, 0.52f);

	glVertex2f(0.27f, 0.52f);

	 glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.20f, 0.57f);
	glVertex2f(0.16f, 0.54f);

	glVertex2f(0.24f, 0.54f);

	 glEnd();
	 glLoadIdentity();
	 }







	// Fear tree 4
	void Day_fear_tree_4(){
	 glLineWidth(12);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(0.6f, 0.5f);
	glVertex2f(0.6f, 0.45f);
glEnd();



	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.60f, 0.54f);
	glVertex2f(0.55f, 0.5f);

	glVertex2f(0.65f, 0.5f);

	 glEnd();




	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.60f, 0.57f);
	glVertex2f(0.55f, 0.52f);

	glVertex2f(0.65f, 0.52f);

	 glEnd();


	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.60f, 0.59f);
	glVertex2f(0.55f, 0.54f);

	glVertex2f(0.65f, 0.54f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(0.60f, 0.64f);
	glVertex2f(0.55f, 0.56f);

	glVertex2f(0.65f, 0.56f);

	 glEnd();
glLoadIdentity();
	}








	//car

//3rd car//
void Day_3rd_car(){
glPushMatrix();
glTranslatef(-position_3rd_car, 0.0f,0.0f);
	glBegin(GL_POLYGON);
	glColor3f(1.0f, 0.0f, 0.0f);

	glVertex2f(-0.25f, 0.45f);
	glVertex2f(-0.3f, 0.4f);

	glVertex2f(-0.3f, 0.35f);
	glVertex2f(-0.07f, 0.35f);


	glVertex2f(-0.07f, 0.37f);
	glVertex2f(-0.1f, 0.4f);

	glVertex2f(-0.15f, 0.45f);
	 glEnd();


	 glBegin(GL_QUADS);
	glColor3f(1.0f, 1.0f, 1.0f);

	glVertex2f(-0.24f, 0.44f);
	glVertex2f(-0.29f, 0.4f);

	glVertex2f(-0.11f, 0.4f);
	glVertex2f(-0.16f, 0.44f);


    glEnd();




	glLineWidth(.5);
	glBegin(GL_LINES);
	glColor3f(1.0f, 0.0f, 0.0f);

	glVertex2f(-0.24f, 0.44f);
	glVertex2f(-0.24f, 0.4f);


	glVertex2f(-0.2f, 0.44f);
	glVertex2f(-0.2f, 0.4f);

    glVertex2f(-0.16f, 0.44f);
	glVertex2f(-0.16f, 0.4f);



	 glEnd();

 // Car3 Taire1//
 int p;

GLfloat g1=-0.25f;
GLfloat g2= 0.35f;
GLfloat r12 = 0.025f;
int triangle12=50;



GLfloat tp12 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.0f, 0.0f, 0.0f);
glVertex2f (g1,g2);
for(p= 0;p<=triangle12; p++)
{
glVertex2f (
g1+(r12*cos(p*tp12/triangle12)),
g2+(r12*sin(p*tp12/triangle12))
);
}
glEnd ();



 int P;

GLfloat g3=-0.25f;
GLfloat g4= 0.35f;
GLfloat R12 = 0.015f;
int Triangle12=50;



GLfloat Tp12 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (g3,g4);
for(P= 0;P<=Triangle12; P++)
{
glVertex2f (
g3+(R12*cos(P*Tp12/Triangle12)),
g4+(R12*sin(P*Tp12/Triangle12))
);
}
glEnd ();

// Car2 Taire2//
 int q;

GLfloat g5=-0.13f;
GLfloat g6= 0.35f;
GLfloat r13 = 0.025f;
int triangle13=50;




GLfloat tp13 =2.0f * PI ;




glBegin (GL_TRIANGLE_FAN);
glColor3f(0.0f, 0.0f, 0.0f);
glVertex2f (g5,g6);
for(q= 0;q<=triangle13; q++)
{
glVertex2f (
g5+(r13*cos(q*tp13/triangle13)),
g6+(r13*sin(q*tp13/triangle13))
);
}
glEnd ();



 int Q;

GLfloat g7=-0.13f;
GLfloat g8= 0.35f;
GLfloat R13 = 0.015f;
int Triangle13=50;



GLfloat Tp13 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (g7,g8);
for(Q= 0;Q<=Triangle13; Q++)
{
glVertex2f (
g7+(R13*cos(Q*Tp13/Triangle13)),
g8+(R13*sin(Q*Tp13/Triangle13))
);
}
glEnd ();

glPopMatrix();
glLoadIdentity();
}




	//2nd car//
	void Day_2rd_car(){
	glPushMatrix();
 glTranslatef(-position5, 0.0f,0.0f);
	glBegin(GL_QUADS);
	glColor3f(0.0f, 1.0f, 1.0f);

	glVertex2f(0.1f, 0.4f);
	glVertex2f(0.1f, 0.35f);

	glVertex2f(0.25f, 0.35f);
	glVertex2f(0.2f, 0.4f);
	 glEnd();



	 glBegin(GL_POLYGON);
	glColor3f(0.0f, 1.0f, 1.0f);

	glVertex2f(0.1f, 0.35f);
	glVertex2f(0.1f, 0.3f);

	glVertex2f(0.28f, 0.30f);
	glVertex2f(0.28f, 0.33f);
	glVertex2f(0.25f, 0.35f);
	 glEnd();



    glBegin(GL_QUADS);
	glColor3f(1.0f, 1.0f, 1.0f);

	glVertex2f(0.11f, 0.39f);
	glVertex2f(0.11f, 0.35f);


	glVertex2f(0.24f, 0.35f);
	glVertex2f(0.19f, 0.39f);


	 glEnd();


	 	glLineWidth(.5);
	glBegin(GL_LINES);
	glColor3f(0.0f, 1.0f, 1.0f);


	glVertex2f(0.14f, 0.39f);
	glVertex2f(0.14f, 0.35f);


	glVertex2f(0.18f, 0.39f);
	glVertex2f(0.18f, 0.35f);

 glEnd();

// Car2 Taire1//
 int l;

GLfloat e1=0.14f;
GLfloat e2= 0.3f;
GLfloat r8 = 0.025f;
int triangle8=50;



GLfloat tp8 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.0f, 0.0f, 0.0f);
glVertex2f (e1,e2);
for(l= 0;l<=triangle8; l++)
{
glVertex2f (
e1+(r8*cos(l*tp8/triangle8)),
e2+(r8*sin(l*tp8/triangle8))
);
}
glEnd ();



 int M;

GLfloat e3=0.14f;
GLfloat e4= 0.3f;
GLfloat R8 = 0.015f;
int Triangle8=50;



GLfloat Tp8 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (e3,e4);
for(M= 0;M<=Triangle8; M++)
{
glVertex2f (
e3+(R8*cos(M*Tp8/Triangle8)),
e4+(R8*sin(M*Tp8/Triangle8))
);
}
glEnd ();

// Car2 Taire2//
 int L;

GLfloat e5=0.22f;
GLfloat e6= 0.3f;
GLfloat r9 = 0.025f;
int triangle9=50;



GLfloat tp9 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.0f, 0.0f, 0.0f);
glVertex2f (e5,e6);
for(L= 0;L<=triangle9; L++)
{
glVertex2f (
e5+(r9*cos(L*tp9/triangle9)),
e6+(r9*sin(L*tp9/triangle9))
);
}
glEnd ();



 int m;

GLfloat e7=0.22f;
GLfloat e8= 0.3f;
GLfloat R9 = 0.015f;
int Triangle9=50;



GLfloat Tp9 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (e7,e8);
for(m= 0;m<=Triangle9; m++)
{
glVertex2f (
e7+(R9*cos(m*Tp9/Triangle9)),
e8+(R9*sin(m*Tp9/Triangle9))
);
}
glEnd ();
glPopMatrix();
glLoadIdentity();
	}



//1st car//
void Day_1rd_car(){
glPushMatrix();
glTranslatef(position6, 0.0f,0.0f);
	glBegin(GL_QUADS);
	glColor3f(1.0f, 0.0f, 1.0f);

	glVertex2f(-0.1f, 0.25f);
	glVertex2f(-0.1f, 0.2f);

	glVertex2f(-0.25f, 0.2f);
	glVertex2f(-0.2f, 0.25f);
	 glEnd();



	 glBegin(GL_POLYGON);
	glColor3f(1.0f, 0.0f, 1.0f);

	glVertex2f(-0.1f, 0.2f);
	glVertex2f(-0.1f, 0.15f);

	glVertex2f(-0.28f, 0.15f);
	glVertex2f(-0.28f, 0.18f);
	glVertex2f(-0.25f, 0.2f);
	 glEnd();



    glBegin(GL_QUADS);
	glColor3f(1.0f, 1.0f, 1.0f);

	glVertex2f(-0.11f, 0.24f);
	glVertex2f(-0.11f, 0.2f);


	glVertex2f(-0.24f, 0.2f);
	glVertex2f(-0.19f, 0.24f);


	 glEnd();


	 	glLineWidth(.5);
	glBegin(GL_LINES);
	glColor3f(1.0f, 0.0f, 1.0f);


	glVertex2f(-0.14f, 0.24f);
	glVertex2f(-0.14f, 0.2f);


	glVertex2f(-0.18f, 0.24f);
	glVertex2f(-0.18f, 0.2f);

 glEnd();

// Car2 Taire1//
 int n;

GLfloat f1=-0.14f;
GLfloat f2= 0.15f;
GLfloat r10 = 0.025f;
int triangle10=50;



GLfloat tp10 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.0f, 0.0f, 0.0f);
glVertex2f (f1,f2);
for(n= 0;n<=triangle10; n++)
{
glVertex2f (
f1+(r10*cos(n*tp10/triangle10)),
f2+(r10*sin(n*tp10/triangle10))
);
}
glEnd ();



 int N;

GLfloat f3=-0.14f;
GLfloat f4= 0.15f;
GLfloat R10 = 0.015f;
int Triangle10=50;



GLfloat Tp10 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (f3,f4);
for(N= 0;N<=Triangle10; N++)
{
glVertex2f (
f3+(R10*cos(N*Tp10/Triangle10)),
f4+(R10*sin(N*Tp10/Triangle10))
);
}
glEnd ();

// Car2 Taire2//
 int o;

GLfloat f5=-0.22f;
GLfloat f6= 0.15f;
GLfloat r11 = 0.025f;
int triangle11=50;



GLfloat tp11 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(0.0f, 0.0f, 0.0f);
glVertex2f (f5,f6);
for(o= 0;o<=triangle11; o++)
{
glVertex2f (
f5+(r11*cos(o*tp11/triangle11)),
f6+(r11*sin(o*tp11/triangle11))
);
}
glEnd ();



 int O;

GLfloat f7=-0.22f;
GLfloat f8= 0.15f;
GLfloat R11 = 0.015f;
int Triangle11=50;



GLfloat Tp11 =2.0f * PI ;



glBegin (GL_TRIANGLE_FAN);
glColor3f(1.0f, 1.0f, 1.0f);
glVertex2f (f7,f8);
for(O= 0;O<=Triangle11; O++)
{
glVertex2f (
f7+(R11*cos(O*Tp11/Triangle11)),
f8+(R11*sin(O*Tp11/Triangle11))
);
}
glEnd ();
glPopMatrix();
glLoadIdentity();
}





//Tree 1
void Day_tree_1(){
glBegin(GL_QUADS);
	glColor3f(0.4f, 0.0f, 0.0f);

	glVertex2f(-0.93f, 0.15f);
	glVertex2f(-0.93f, 0.0f);

	glVertex2f(-0.87f, 0.0f);
	glVertex2f(-0.87f, 0.15f);
	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.90f, 0.25f);
	glVertex2f(-1.0f, 0.15f);

	glVertex2f(-0.80f, 0.15f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.90f, 0.35f);
	glVertex2f(-1.0f, 0.2f);

	glVertex2f(-0.80f, 0.2f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.90f, 0.45f);
	glVertex2f(-1.0f, 0.25f);

	glVertex2f(-0.80f, 0.25f);

	 glEnd();



	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.90f, 0.5f);
	glVertex2f(-1.0f, 0.3f);

	glVertex2f(-0.80f, 0.3f);

	 glEnd();
	 glLoadIdentity();
}



	 //tree 2
	 void Day_tree_2(){
	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.60f, 0.22f);
	glVertex2f(-0.75f, 0.15f);

	glVertex2f(-0.45f, 0.15f);

	 glEnd();


	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.60f, 0.27f);
	glVertex2f(-0.7f, 0.20f);

	glVertex2f(-0.5f, 0.20f);

	 glEnd();


	   glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.60f, 0.32f);
	glVertex2f(-0.65f, 0.25f);

	glVertex2f(-0.55f, 0.25f);

	 glEnd();
glLoadIdentity();
	 }




	 //tree 3//
	 void Day_tree_3(){
	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.25f, 0.22f);
	glVertex2f(-0.40f, 0.15f);

	glVertex2f(-0.1f, 0.15f);

	 glEnd();


	  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.25f, 0.27f);
	glVertex2f(-0.35f, 0.20f);

	glVertex2f(-0.15f, 0.20f);

	 glEnd();


	   glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.25f, 0.32f);
	glVertex2f(-0.3f, 0.25f);

	glVertex2f(-0.2f, 0.25f);

	 glEnd();
	 glLoadIdentity();
	 }








//House 1
void Day_house_1(){

glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.65f, 0.15f);
	glVertex2f(-0.74f, 0.07f);

	glVertex2f(-0.72f, 0.05f);
	glVertex2f(-0.63f, 0.13f);
	 glEnd();


glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.65f, 0.15f);
	glVertex2f(-0.6f, 0.05f);

	glVertex2f(-0.3f, 0.05f);
	glVertex2f(-0.4f, 0.15f);
	 glEnd();


	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.7f, 0.2f);

	glVertex2f(-0.6f, 0.05f);
	glVertex2f(-0.6f, -0.1f);

	glVertex2f(-0.35f, -0.05f);
	glVertex2f(-0.35f, 0.05f);
	 glEnd();



	 glBegin(GL_POLYGON);
	glColor3f(0.7f, 0.6f, 0.1f);

	glVertex2f(-0.63f, 0.13f);
	glVertex2f(-0.7f, 0.07f);

	glVertex2f(-0.7f, -0.05f);
	glVertex2f(-0.6f, -0.1f);

	glVertex2f(-0.6f, 0.05f);

	 glEnd();


//window1
	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.67f, 0.05f);
	glVertex2f(-0.67f, 0.0f);

	glVertex2f(-0.63f, -0.02f);
	glVertex2f(-0.63f, 0.03f);
	 glEnd();

//door
	 	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.51f, 0.01f);
	glVertex2f(-0.51f, -0.08f);

	glVertex2f(-0.45f, -0.07f);
	glVertex2f(-0.45f, 0.01f);
	 glEnd();


	 //window2
	  glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.58f, 0.01f);
	glVertex2f(-0.58f, -0.03f);

	glVertex2f(-0.53f, -0.03f);
	glVertex2f(-0.53f, 0.01f);
	 glEnd();


	 //window3
	  glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.43f, 0.01f);
	glVertex2f(-0.43f, -0.025f);

	glVertex2f(-0.38f, -0.025f);
	glVertex2f(-0.38f, 0.01f);
	 glEnd();
glLoadIdentity();
}



	 //House 2//
void Day_house_2(){
	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.35f, 0.15f);
	glVertex2f(-0.44f, 0.07f);

	glVertex2f(-0.42f, 0.05f);
	glVertex2f(-0.33f, 0.13f);
	 glEnd();


glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.35f, 0.15f);
	glVertex2f(-0.3f, 0.05f);

	glVertex2f(0.0f, 0.05f);
	glVertex2f(-0.1f, 0.15f);
	 glEnd();


	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.7f, 0.6f);

	glVertex2f(-0.3f, 0.05f);
	glVertex2f(-0.3f, -0.1f);
	glVertex2f(-0.05f, -0.05f);
	glVertex2f(-0.05f, 0.05f);
	 glEnd();



	 glBegin(GL_POLYGON);
	glColor3f(0.7f, 0.6f, 0.5f);

	glVertex2f(-0.33f, 0.13f);
	glVertex2f(-0.4f, 0.07f);

	glVertex2f(-0.4f, -0.062f);
	glVertex2f(-0.3f, -0.1f);

	glVertex2f(-0.3f, 0.05f);

	 glEnd();


	 //window1
	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.37f, 0.04f);
	glVertex2f(-0.37f, -0.01f);

	glVertex2f(-0.33f, -0.02f);
	glVertex2f(-0.33f, 0.03f);
	 glEnd();


	 //door
	 	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.21f, 0.01f);
	glVertex2f(-0.21f, -0.08f);

	glVertex2f(-0.15f, -0.07f);
	glVertex2f(-0.15f, 0.01f);
	 glEnd();


	 //window2
	  glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.28f, 0.01f);
	glVertex2f(-0.28f, -0.03f);

	glVertex2f(-0.23f, -0.03f);
	glVertex2f(-0.23f, 0.01f);
	 glEnd();


	 //window3
	  glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.13f, 0.01f);
	glVertex2f(-0.13f, -0.025f);

	glVertex2f(-0.08f, -0.025f);
	glVertex2f(-0.08f, 0.01f);
	 glEnd();
glLoadIdentity();
}


	 //House 3//
void Day_house_3(){
	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.90f, -0.35f);
	glVertex2f(-0.99f, -0.43f);

	glVertex2f(-0.97f, -0.45f);
	glVertex2f(-0.88f, -0.37f);
	 glEnd();


glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.90f, -0.35f);
	glVertex2f(-0.85f, -0.45f);

	glVertex2f(-0.55f, -0.45f);
	glVertex2f(-0.65f, -0.35f);
	 glEnd();


	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.7f, 0.6f);

	glVertex2f(-0.85f, -0.45f);
	glVertex2f(-0.85f, -0.6f);

	glVertex2f(-0.6f, -0.55f);
	glVertex2f(-0.6f, -0.45f);
	 glEnd();



	 glBegin(GL_POLYGON);
	glColor3f(0.7f, 0.6f, 0.5f);

	glVertex2f(-0.88f, -0.37f);
	glVertex2f(-0.95f, -0.42f);

	glVertex2f(-0.95f, -0.55f);
	glVertex2f(-0.85f, -0.6f);

	glVertex2f(-0.85f, -0.45f);

	 glEnd();


	 //Door//

	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.76f, -0.49f);
	glVertex2f(-0.76f, -0.58f);

	glVertex2f(-0.7f, -0.57);
	glVertex2f(-0.7f, -0.49f);
	 glEnd();



	 //window1
	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.92f, -0.45f);
	glVertex2f(-0.92f, -0.50f);
	glVertex2f(-0.88f, -0.52f);
	glVertex2f(-0.88f, -0.47f);
	 glEnd();

	 	 //window2
	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.83f, -0.49f);
	glVertex2f(-0.83f, -0.53f);

	glVertex2f(-0.78f, -0.53f);
	glVertex2f(-0.78f, -0.49f);
	 glEnd();



	 	 //window3
	 glBegin(GL_QUADS);
	glColor3f(0.8f, 0.9f, 0.9f);

	glVertex2f(-0.68f, -0.49f);
	glVertex2f(-0.68f, -0.525f);

	glVertex2f(-0.63f, -0.525f);
	glVertex2f(-0.63f, -0.49f);
	 glEnd();

glLoadIdentity();
}





//House 4//
void Day_house_4(){

glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.31f, -0.36f);
	glVertex2f(-0.23f, -0.45f);

	glVertex2f(-0.22f, -0.44f);
	glVertex2f(-0.30f, -0.35f);
	 glEnd();


glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.55f, -0.35f);
	glVertex2f(-0.65f, -0.45f);

	glVertex2f(-0.35f, -0.45f);
	glVertex2f(-0.30f, -0.35f);
	 glEnd();


	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.6f, 0.1f);

	glVertex2f(-0.6f, -0.45f);
	glVertex2f(-0.6f, -0.55f);

	glVertex2f(-0.35f, -0.6f);
	glVertex2f(-0.35f, -0.45f);
	 glEnd();



	 glBegin(GL_POLYGON);
	glColor3f(0.8f, 0.7f, 0.2f);

	glVertex2f(-0.31f, -0.36f);
	glVertex2f(-0.35f, -0.45f);

	glVertex2f(-0.35f, -0.6f);
	glVertex2f(-0.25f, -0.55f);

	glVertex2f(-0.25f, -0.43f);

	 glEnd();


	 //window1
	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.28f,-0.45f);
	glVertex2f(-0.28f, -0.50f);

	glVertex2f(-0.315f, -0.51f);
	glVertex2f(-0.315f, -0.46f);
	 glEnd();


	 //Door//
	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.50f,-0.49f);
	glVertex2f(-0.50f, -0.57f);

	glVertex2f(-0.44f, -0.585f);
	glVertex2f(-0.44f, -0.49f);
	 glEnd();



	 //window2
	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.37f,-0.49);
	glVertex2f(-0.37f, -0.535f);

	glVertex2f(-0.42f, -0.535f);
	glVertex2f(-0.42f, -0.49f);
	 glEnd();



	  //window3
	 glBegin(GL_QUADS);
	glColor3f(0.7f, 0.8f, 0.8f);

	glVertex2f(-0.57f,-0.485);
	glVertex2f(-0.57f, -0.52f);

	glVertex2f(-0.52f, -0.53f);
	glVertex2f(-0.52f, -0.49f);
	 glEnd();
	 glLoadIdentity();
}



//Tree for 3 and 4 house

void Day_tree_4(){
 glBegin(GL_TRIANGLES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(-0.65f,-0.35f);
	glVertex2f(-0.6f, -0.4f);

	glVertex2f(-0.55f, -0.35f);

	 glEnd();




	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.6f,-0.25f);
	glVertex2f(-0.75f, -0.35f);

	glVertex2f(-0.45f, -0.35f);

	 glEnd();



	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.6f,-0.15f);
	glVertex2f(-0.75f, -0.3f);

	glVertex2f(-0.45f, -0.3f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.6f,-0.05f);
	glVertex2f(-0.75f, -0.25f);

	glVertex2f(-0.45f, -0.25f);

	 glEnd();



 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.50f, 0.0f);

	glVertex2f(-0.6f,0.0f);
	glVertex2f(-0.75f, -0.2f);

	glVertex2f(-0.45f, -0.2f);

	 glEnd();
glLoadIdentity();
}


void Night_tree_4(){
 glBegin(GL_TRIANGLES);
	glColor3f(0.30f, 0.0f, 0.0f);

	glVertex2f(-0.65f,-0.35f);
	glVertex2f(-0.6f, -0.4f);

	glVertex2f(-0.55f, -0.35f);

	 glEnd();




	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.30f, 0.0f);

	glVertex2f(-0.6f,-0.25f);
	glVertex2f(-0.75f, -0.35f);

	glVertex2f(-0.45f, -0.35f);

	 glEnd();



	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.30f, 0.0f);

	glVertex2f(-0.6f,-0.15f);
	glVertex2f(-0.75f, -0.3f);

	glVertex2f(-0.45f, -0.3f);

	 glEnd();


	 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.30f, 0.0f);

	glVertex2f(-0.6f,-0.05f);
	glVertex2f(-0.75f, -0.25f);
	glVertex2f(-0.45f, -0.25f);

	 glEnd();



 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.30f, 0.0f);

	glVertex2f(-0.6f,0.0f);
	glVertex2f(-0.75f, -0.2f);

	glVertex2f(-0.45f, -0.2f);

	 glEnd();
glLoadIdentity();
}




	 //Khajur  tree



	 void Day_khajur_tree(){
	  glBegin(GL_QUADS);
	glColor3f(0.6f, 0.0f, 0.0f);

	glVertex2f(0.02f, 0.15f);
	glVertex2f(0.02f, -0.67f);

	glVertex2f(0.05f, -0.67f);
	glVertex2f(0.05f, 0.15f);
	 glEnd();




	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.05f, 0.19f);
	glVertex2f(0.05f, 0.15f);
	glVertex2f(0.1f, 0.15f);

	glVertex2f(0.20f, -0.1f);

	glVertex2f(0.2f, -0.075f);

	glVertex2f(0.22f, -0.09f);
	glVertex2f(0.09f, 0.19f);

	 glEnd();





	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.02f, 0.19f);
	glVertex2f(-0.02f, 0.19f);

    glVertex2f(-0.15f, -0.09f);

    glVertex2f(-0.13f, -0.075f);

	glVertex2f(-0.13f, -0.1f);

	glVertex2f(-0.03f, 0.15f);
	glVertex2f(0.02f, 0.15f);

 glEnd();



	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.05f, 0.29f);
	glVertex2f(0.05f, 0.24f);

    glVertex2f(0.1f, 0.24f);

    glVertex2f(0.20f, 0.1f);

	glVertex2f(0.20f, 0.135f);

	glVertex2f(0.22f, 0.11f);
	glVertex2f(0.09f, 0.29f);
 glEnd();





	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.02f, 0.29f);
	glVertex2f(-0.02f, 0.29f);
    glVertex2f(-0.15f, 0.11f);

    glVertex2f(-0.13f, 0.135f);

	glVertex2f(-0.13f, 0.1f);

	glVertex2f(-0.03f, 0.24f);
	glVertex2f(0.02f, 0.24f);

 glEnd();




	  glBegin(GL_QUADS);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.02f, 0.28f);
	glVertex2f(0.02f, 0.15f);

    glVertex2f(0.05f, 0.15f);

    glVertex2f(0.05f, 0.28f);
    glEnd();



	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.02f, 0.28f);
    glVertex2f(0.05f, 0.28f);
    glVertex2f(0.15f, 0.38f);
    glVertex2f(0.125f, 0.41f);
	glVertex2f(0.14f, 0.46f);




 glEnd();





	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.5f, 0.0f);

	glVertex2f(0.05f, 0.28f);
    glVertex2f(-0.07f, 0.46f);
    glVertex2f(-0.065f, 0.41f);
    glVertex2f(-0.08f, 0.38f);
	glVertex2f(0.02f, 0.28f);

 glEnd();
 glLoadIdentity();
}


void Night_khajur_tree(){
	  glBegin(GL_QUADS);
	glColor3f(0.4f, 0.0f, 0.0f);

	glVertex2f(0.02f, 0.15f);
	glVertex2f(0.02f, -0.67f);

	glVertex2f(0.05f, -0.67f);
	glVertex2f(0.05f, 0.15f);
	 glEnd();




	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.05f, 0.19f);
	glVertex2f(0.05f, 0.15f);

	glVertex2f(0.1f, 0.15f);

	glVertex2f(0.20f, -0.1f);

	glVertex2f(0.2f, -0.075f);

	glVertex2f(0.22f, -0.09f);
	glVertex2f(0.09f, 0.19f);

	 glEnd();





	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.02f, 0.19f);
	glVertex2f(-0.02f, 0.19f);

    glVertex2f(-0.15f, -0.09f);

    glVertex2f(-0.13f, -0.075f);

	glVertex2f(-0.13f, -0.1f);

	glVertex2f(-0.03f, 0.15f);
	glVertex2f(0.02f, 0.15f);

 glEnd();



	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.05f, 0.29f);
	glVertex2f(0.05f, 0.24f);

    glVertex2f(0.1f, 0.24f);

    glVertex2f(0.20f, 0.1f);

	glVertex2f(0.20f, 0.135f);

	glVertex2f(0.22f, 0.11f);
	glVertex2f(0.09f, 0.29f);
 glEnd();





	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.02f, 0.29f);
	glVertex2f(-0.02f, 0.29f);

    glVertex2f(-0.15f, 0.11f);

    glVertex2f(-0.13f, 0.135f);

	glVertex2f(-0.13f, 0.1f);
	glVertex2f(-0.03f, 0.24f);
	glVertex2f(0.02f, 0.24f);

 glEnd();




	  glBegin(GL_QUADS);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.02f, 0.28f);
	glVertex2f(0.02f, 0.15f);
    glVertex2f(0.05f, 0.15f);

    glVertex2f(0.05f, 0.28f);
    glEnd();



	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.02f, 0.28f);
    glVertex2f(0.05f, 0.28f);
    glVertex2f(0.15f, 0.38f);
    glVertex2f(0.125f, 0.41f);
	glVertex2f(0.14f, 0.46f);




 glEnd();





	  glBegin(GL_POLYGON);
	glColor3f(0.0f, 0.3f, 0.0f);

	glVertex2f(0.05f, 0.28f);
    glVertex2f(-0.07f, 0.46f);
    glVertex2f(-0.065f, 0.41f);
    glVertex2f(-0.08f, 0.38f);
	glVertex2f(0.02f, 0.28f);
 glEnd();
 glLoadIdentity();
}




 //Boat1//
 void Day_boat_1(){
glPushMatrix();
glTranslatef(-position8, 0.0f,0.0f);
	  glBegin(GL_POLYGON);
	glColor3f(0.9f, 0.9f, 0.14f);

    glVertex2f(0.16f, -0.92f);
    glVertex2f(-0.16f, -0.92f);


	glVertex2f(-0.15f, -0.95f);
	glVertex2f(0.15f, -0.95f);
    glVertex2f(0.25f, -0.85f);

 glEnd();

 glBegin(GL_TRIANGLES);
	glColor3f(0.9f, 0.9f, 0.14f);


    glVertex2f(-0.16f, -0.92f);
    glVertex2f(-0.25f, -0.85f);
    glVertex2f(-0.15f, -0.95f);

 glEnd();


 glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.0f, 0.0f);


    glVertex2f(0.13f, -0.80f);
    glVertex2f(0.1f, -0.92f);
    glVertex2f(0.16f, -0.92f);

 glEnd();



	  glBegin(GL_QUADS);
	glColor3f(0.7f, 0.7f, 0.14f);

    glVertex2f(-0.1f, -0.80f);
    glVertex2f(-0.16f, -0.92f);


	glVertex2f(0.1f, -0.92f);
	glVertex2f(0.13f, -0.80f);
     glEnd();



	  glBegin(GL_QUADS);
	glColor3f(1.0f, 0.0f, 0.14f);

    glVertex2f(-0.105f, -0.66f);
    glVertex2f(-0.055f, -0.80f);


	glVertex2f(0.085f, -0.80f);
	glVertex2f(0.035f, -0.66f);
	 glEnd();



	 glLineWidth(5);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(-0.02f, -0.62f);
	glVertex2f(-0.02f, -0.66f);
    glEnd();
glPopMatrix();
glLoadIdentity();
 }


//Boat 2//
void Day_boat_2(){

 glBegin(GL_POLYGON);
	glColor3f(0.9f, 0.9f, 0.14f);

    glVertex2f(0.50f, -0.35f);
    glVertex2f(0.42f, -0.3f);


	glVertex2f(0.51f, -0.38f);
	glVertex2f(0.64f, -0.38f);
    glVertex2f(0.65f, -0.35f);

 glEnd();


  glBegin(GL_TRIANGLES);
	glColor3f(0.9f, 0.9f, 0.14f);


    glVertex2f(0.65f, -0.35f);
    glVertex2f(0.64f, -0.38f);
    glVertex2f(0.72f, -0.3f);

 glEnd();

  glBegin(GL_TRIANGLES);
	glColor3f(0.0f, 0.0f, 0.0f);


    glVertex2f(0.525f, -0.25f);
    glVertex2f(0.50f, -0.35f);
    glVertex2f(0.55f, -0.35f);

 glEnd();


   glBegin(GL_QUADS);
	glColor3f(1.0f, 0.60f, 0.14f);

    glVertex2f(0.525f, -0.25f);
    glVertex2f(0.55f, -0.35f);


	glVertex2f(0.65f, -0.35f);
	glVertex2f(0.625f, -0.25f);
	 glEnd();



	 glLineWidth(5);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(0.48f, -0.25f);
	glVertex2f(0.50f, -0.42f);
    glEnd();


	 glLineWidth(7);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(0.12f, -0.25f);
	glVertex2f(0.12f, -0.42f);
    glEnd();



    	 glLineWidth(3);
	glBegin(GL_LINES);
	glColor3f(0.40f, 0.0f, 0.0f);

	glVertex2f(0.12f, -0.35f);
	glVertex2f(0.49f, -0.35f);
    glEnd();
    glLoadIdentity();
}

void Stars(){

    glPointSize(3);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 1.0f, 1.0f);

	glVertex2f(-0.9f, 0.9f);
	glVertex2f(-0.7f, 0.85f);
	glVertex2f(-0.8f, 0.8f);
	glVertex2f(-0.6f, 0.75f);
	glVertex2f(-0.5f, 0.7f);
	glVertex2f(-0.4f, 0.65f);
	glVertex2f(-0.2f, 0.6f);
	glVertex2f(-0.1f, 0.55f);
	glVertex2f(-0.3f, 0.5f);
	glVertex2f(0.0f, 0.45f);
	glVertex2f(0.9f, 0.9f);
	glVertex2f(0.7f, 0.85f);
	glVertex2f(0.4f, 0.8f);
	glVertex2f(0.5f, 0.75f);
	glVertex2f(0.3f, 0.7f);
	glVertex2f(0.8f, 0.65f);
	glVertex2f(0.1f, 0.6f);
	glVertex2f(-0.9f, 0.55f);
	glVertex2f(-0.8f, 0.5f);
	glVertex2f(-0.4f, 0.45f);


		glVertex2f(-0.5f, 0.9f);
	glVertex2f(-0.4f, 0.85f);
	glVertex2f(-0.2f, 0.8f);
	glVertex2f(0.0f, 0.75f);
	glVertex2f(0.2f, 0.7f);

	glVertex2f(0.2f, 0.45f);
glEnd();
glLoadIdentity();

}




bool snowday=false;

void Snow()
{

if (snowday==true){
  glPushMatrix();
  glTranslatef(0.0f, position_snow, 0.0f);
 glPointSize(8.5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 1.0f, 1.0f);

	glVertex2f(-0.9f, 0.9f);
	glVertex2f(-0.7f, 0.85f);
	glVertex2f(-0.8f, 0.8f);
	glVertex2f(-0.6f, 0.75f);
	glVertex2f(-0.5f, 0.7f);
	glVertex2f(-0.4f, 0.65f);
	glVertex2f(-0.2f, 0.6f);
	glVertex2f(-0.1f, 0.55f);
	glVertex2f(-0.3f, 0.5f);
	glVertex2f(0.0f, 0.45f);
	glVertex2f(0.9f, 0.9f);
	glVertex2f(0.7f, 0.85f);
	glVertex2f(0.4f, 0.8f);
	glVertex2f(0.5f, 0.75f);
	glVertex2f(0.3f, 0.7f);
	glVertex2f(0.8f, 0.65f);
	glVertex2f(0.1f, 0.6f);
	glVertex2f(-0.9f, 0.55f);
	glVertex2f(-0.8f, 0.5f);
	glVertex2f(-0.4f, 0.45f);


		glVertex2f(-0.5f, 0.9f);
	glVertex2f(-0.4f, 0.85f);
	glVertex2f(-0.2f, 0.8f);
	glVertex2f(0.0f, 0.75f);
	glVertex2f(0.2f, 0.7f);


	glVertex2f(0.9f, -0.9f);
	glVertex2f(0.7f, 0.05f);
	glVertex2f(0.8f, -0.8f);
	glVertex2f(0.6f, -0.75f);
	glVertex2f(0.5f, 0.0f);
	glVertex2f(0.4f, -0.65f);
	glVertex2f(0.2f, -0.6f);
	glVertex2f(0.1f, -0.55f);
	glVertex2f(0.3f, 0.025f);

	glVertex2f(0.2f, 0.45f);



	glVertex2f(0.0f, -0.45f);
	glVertex2f(-0.9f, -0.9f);
	glVertex2f(-0.7f, -0.85f);
	glVertex2f(-0.4f, -0.8f);
	glVertex2f(-0.5f, -0.75f);
	glVertex2f(-0.3f, -0.7f);
	glVertex2f(-0.8f, -0.65f);
	glVertex2f(-0.1f, -0.6f);
	glVertex2f(0.9f, -0.55f);
	glVertex2f(0.8f, -0.5f);
	glVertex2f(0.4f, -0.45f);
    glVertex2f(-0.4f, 0.0f);
	glVertex2f(-0.5f, 0.3f);
	glVertex2f(-0.3f, 0.17f);


		glVertex2f(0.5f, -0.9f);
	glVertex2f(0.4f, -0.85f);
	glVertex2f(0.2f, -0.8f);
	glVertex2f(-0.0f, -0.75f);
	glVertex2f(-0.2f, -0.7f);
    glVertex2f(-0.6f, -1.0f);
     glVertex2f(-0.6f, -0.80f);
  glVertex2f(-0.6f, -0.40f);



glEnd();
glPopMatrix();



	glutPostRedisplay();




}
glFlush();
}







void Rain()
{
     if(rainday==true)
    {

        glPushMatrix();
        glTranslatef(0.0, 0.5f, 0.0f);

          glPushMatrix();
        glTranslatef(0.0, position_rain, 0.0f);
        for(float i=1.0f; i>=-1.5f; i-=0.05f)
        {
            for(float j=-1.0f; j<=1.5f; j+=0.05f)
            {
                glLineWidth(3);
                glBegin(GL_LINES);
                glColor3f(1.0f,1.0f,1.0f);
                glVertex2f(j+0.01,i);
                glVertex2f(j,i+0.02);
                glEnd();
            }
        }
        glPopMatrix();
        glPopMatrix();

    }
    position_rain-=0.05;
    glFlush();
}

void Flower()
{
    if(flower==true)
    {

    glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 1.0f);

	glVertex2f(-0.9f, 0.35f);
	glVertex2f(-0.905f, 0.36f);
	glVertex2f(-0.895f, 0.36f);
	glVertex2f(-0.905f, 0.34f);
	glVertex2f(-0.895f, 0.34f);

                glEnd();

                glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 0.0f);

	glVertex2f(-0.84f, 0.35f);
	glVertex2f(-0.845f, 0.36f);
	glVertex2f(-0.835f, 0.36f);
	glVertex2f(-0.845f, 0.34f);
	glVertex2f(-0.835f, 0.34f);

                glEnd();


                 glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 1.0f, 0.0f);

	glVertex2f(-0.84f, 0.25f);
	glVertex2f(-0.845f, 0.26f);
	glVertex2f(-0.835f, 0.26f);
	glVertex2f(-0.845f, 0.24f);
	glVertex2f(-0.835f, 0.24f);

                glEnd();




                 glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.40f, 0.30f);

	glVertex2f(-0.94f, 0.25f);
	glVertex2f(-0.945f, 0.26f);
	glVertex2f(-0.935f, 0.26f);
	glVertex2f(-0.945f, 0.24f);
	glVertex2f(-0.935f, 0.24f);

                glEnd();


                 glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(0.0f, 1.0f, 1.0f);

	glVertex2f(-0.90f, 0.45f);
	glVertex2f(-0.905f, 0.46f);
	glVertex2f(-0.895f, 0.46f);
	glVertex2f(-0.905f, 0.44f);
	glVertex2f(-0.895f, 0.44f);

                glEnd();

                 glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 1.0f, .6f);

	glVertex2f(-0.95f, 0.35f);
	glVertex2f(-0.955f, 0.36f);
	glVertex2f(-0.945f, 0.36f);
	glVertex2f(-0.955f, 0.34f);
	glVertex2f(-0.945f, 0.34f);

                glEnd();


                 glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 1.0f, .6f);
    glVertex2f(-0.6f,-0.06f);
    glVertex2f(-0.605f,-0.05f);
    glVertex2f(-0.595,-0.05f);
    glVertex2f(-0.605f,-0.07f);
    glVertex2f(-0.595f,-0.07f);
    glEnd();


                 glPointSize(6.5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 1.0f);
    glVertex2f(-0.65f,-0.11f);
    glVertex2f(-0.655f,-0.10f);
    glVertex2f(-0.645,-0.10f);
    glVertex2f(-0.655f,-0.12f);
    glVertex2f(-0.645f,-0.12f);
    glEnd();


       glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 0.0f);
    glVertex2f(-0.6f,-0.21f);
    glVertex2f(-0.605f,-0.20f);
    glVertex2f(-0.595,-0.20f);
    glVertex2f(-0.605f,-0.22f);
    glVertex2f(-0.595f,-0.22f);
    glEnd();




                 glPointSize(6.5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.50f, 1.0f);
    glVertex2f(-0.65f,-0.31f);
    glVertex2f(-0.655f,-0.30f);
    glVertex2f(-0.645,-0.30f);
    glVertex2f(-0.655f,-0.32f);
    glVertex2f(-0.645f,-0.32f);
    glEnd();



                 glPointSize(6.5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.50f, .70f);
    glVertex2f(-0.55f,-0.31f);
    glVertex2f(-0.555f,-0.30f);
    glVertex2f(-0.545,-0.30f);
    glVertex2f(-0.555f,-0.32f);
    glVertex2f(-0.545f,-0.32f);
    glEnd();



    glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.50f, .70f);
    glVertex2f(-0.58f,0.21f);
    glVertex2f(-0.585f,0.20f);
    glVertex2f(-0.575,0.20f);
    glVertex2f(-0.585f,0.22f);
    glVertex2f(-0.575f,0.22f);
    glEnd();


    glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(0.70f, 0.70f, .70f);
    glVertex2f(-0.61f,0.25f);
    glVertex2f(-0.615f,0.26f);
    glVertex2f(-0.605,0.26f);
    glVertex2f(-0.615f,0.24f);
    glVertex2f(-0.605f,0.24f);
    glEnd();


     glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 1.0f);
    glVertex2f(-0.28f,0.21f);
    glVertex2f(-0.285f,0.20f);
    glVertex2f(-0.275,0.20f);
    glVertex2f(-0.285f,0.22f);
    glVertex2f(-0.275f,0.22f);
    glEnd();



    glPointSize(6);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 0.0f);
    glVertex2f(-0.25f,0.25f);
    glVertex2f(-0.255f,0.26f);
    glVertex2f(-0.245,0.26f);
    glVertex2f(-0.255f,0.24f);
    glVertex2f(-0.245f,0.24f);
    glEnd();


     glPointSize(5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 0.0f);
    glVertex2f(-0.6f,0.54f);
    glVertex2f(-0.605f,0.55f);
    glVertex2f(-0.595,0.55f);
    glVertex2f(-0.605f,0.53f);
    glVertex2f(-0.595f,0.53f);
    glEnd();


     glPointSize(5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 1.0f);
    glVertex2f(-0.2f,0.55f);
    glVertex2f(-0.205f,0.56f);
    glVertex2f(-0.195,0.56f);
    glVertex2f(-0.205f,0.54f);
    glVertex2f(-0.195f,0.54f);
    glEnd();

    glPointSize(5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 0.0f);
    glVertex2f(0.2f,0.54f);
    glVertex2f(0.205f,0.55f);
    glVertex2f(0.195,0.55f);
    glVertex2f(0.205f,0.53f);
    glVertex2f(0.195f,0.53f);
    glEnd();


         glPointSize(5);
	glBegin(GL_POINTS);
    glColor3f(1.0f, 0.0f, 1.0f);
    glVertex2f(0.6f,0.56f);
    glVertex2f(0.605f,0.57f);
    glVertex2f(0.595,0.57f);
    glVertex2f(0.605f,0.55f);
    glVertex2f(0.595f,0.55f);
    glEnd();
            }


    glFlush();
}

void handleMouse(int button, int state, int x, int y) {
if (button == GLUT_LEFT_BUTTON)
{	speed1 += 0.01f;
}
if (button == GLUT_RIGHT_BUTTON)
{speed1 -= 0.01f;   }

if (button == GLUT_LEFT_BUTTON)
{	speed2 += 0.02f;
}
if (button == GLUT_RIGHT_BUTTON)
{speed2 -= 0.02f;   }
if (button == GLUT_LEFT_BUTTON)
{	speed3 += 0.03f;
}
if (button == GLUT_RIGHT_BUTTON)
{
    speed3 -= 0.03f;
 }
 if (button == GLUT_LEFT_BUTTON)
{	speed4 += 0.03f;
}
if (button == GLUT_RIGHT_BUTTON)
{speed4 -= 0.03;   }

if (button == GLUT_LEFT_BUTTON)
{	speed5 += 0.025f;
}
if (button == GLUT_RIGHT_BUTTON)
{speed5 -= 0.025f;   }
if (button == GLUT_LEFT_BUTTON)
{	speed6 += 0.017f;
}
if (button == GLUT_RIGHT_BUTTON)
{
    speed6 -= 0.017f;
 }

 if (button == GLUT_LEFT_BUTTON)
{	speed_3rd_car += 0.02f;
}
if (button == GLUT_RIGHT_BUTTON)
{speed_3rd_car -= 0.02f;   }
if (button == GLUT_LEFT_BUTTON)
{	speed8 += 0.003f;
}
if (button == GLUT_RIGHT_BUTTON)
{
    speed8 -= 0.003f;
 }


glutPostRedisplay();
}








///VIEWS

void load_Restart(int x)
{
    glutDisplayFunc(load_Start);
}





void View_Night() ///NIGHT TIME
{
	glClearColor(1.0f, 1.0f, 1.0f, 1.0f);
    glClear(GL_COLOR_BUFFER_BIT);
glLoadIdentity();
Rainy_Night_Sky();
 Rainy_Clouds();
if(rainday==false)
    {
    Night_sky();
    }
     if(rainday==false){
    Stars();
     }
      if(rainday==false){
    Moon();
      }
       if(rainday==false){
    Clouds_1();
       }
        if(rainday==false){
    Clouds_2();
        }

    Night_river();
   Night_grass();
    Night_road();
    Day_hill();

    Day_3rd_car();
    Day_2rd_car();
    Day_1rd_car();

    Day_house_1();
    Day_house_2();
    Day_house_3();
    Day_house_4();
    Day_fear_tree_1();
    Day_fear_tree_2();
    Day_fear_tree_3();
    Day_fear_tree_4();
   Night_khajur_tree();
    Day_tree_1();
    Day_tree_2();
    Day_tree_3();
    Night_tree_4();
    Day_boat_1();
    Day_boat_2();

    Flower();

  Snow();
  Rain();


glutTimerFunc(5500,load_Restart,0);
    position_sun = 0.0f;

    glFlush();
}

void load_Night(int x)
{
    glutDisplayFunc(View_Night);
}

void View_Evening() ///EVENING TIME
{
	glClearColor(1.0f, 1.0f, 1.0f, 1.0f);
    glClear(GL_COLOR_BUFFER_BIT);
    Rainy_Sky();
     Rainy_Clouds();
     if(rainday==false){
   Evening_sky();
     }
 if(rainday==false){
    Sun();
 }
 if(rainday==false){
    Clouds_1();
 }
  if(rainday==false){
    Clouds_2();
  }
     if(rainday==false){
    Bird_1();
     }
      if(rainday==false){
    Bird_3();
      }

    Day_river();
    Day_grass();
    Day_road();
    Day_hill();

    Day_3rd_car();
    Day_2rd_car();
    Day_1rd_car();



    Day_house_1();
    Day_house_2();
    Day_house_3();
    Day_house_4();
    Day_fear_tree_1();
    Day_fear_tree_2();
    Day_fear_tree_3();
    Day_fear_tree_4();
    Day_khajur_tree();
    Day_tree_1();
    Day_tree_2();
    Day_tree_3();
    Day_tree_4();
    Day_boat_1();
    Day_boat_2();

    Flower();
    Snow();
    Rain();

    glutTimerFunc(5500,load_Night,0);
    position_moon = 0.0f;


    glFlush();
}

void load_Evening(int x)
{
    glutDisplayFunc(View_Evening);
}



void View_Day() ///DAY TIME
{
    glClearColor(1.0f, 1.0f, 1.0f, 0.0f);
    glClear(GL_COLOR_BUFFER_BIT);
glLoadIdentity();
Rainy_Sky();
Rainy_Clouds();
 if(rainday==false){
    Day_sky();
 }
    if(rainday==false){
    Sun();
    }
 if(rainday==false){
    Clouds_1();
 }
  if(rainday==false){
    Clouds_2();
  }
     if(rainday==false){
    Bird_1();
     }
      if(rainday==false){
    Bird_3();
      }
    Day_river();
    Day_grass();
    Day_road();
    Day_hill();

    Day_3rd_car();
    Day_2rd_car();
    Day_1rd_car();


    Day_house_1();
    Day_house_2();
    Day_house_3();
    Day_house_4();
    Day_fear_tree_1();
    Day_fear_tree_2();
    Day_fear_tree_3();
    Day_fear_tree_4();
    Day_khajur_tree();
    Day_tree_1();
    Day_tree_2();
    Day_tree_3();
    Day_tree_4();
    Day_boat_1();
    Day_boat_2();

    Flower();

      Snow();
    Rain();

    glutTimerFunc(5500,load_Evening,0);
    glFlush();
}
void load_Day(int x)
{
    glutDisplayFunc(View_Day);
}


void load_Start()
{
    glutDisplayFunc(View_Day);
}


void handleKeypress(unsigned char key, int x, int y) {
switch (key) {
case 'a':
    speed1 = 0.0f;
    break;
case 'b':
    speed1 = 0.01f;
    break;

    case 'c':
    speed2 = 0.0f;
    break;
case 'd':
   speed2 = 0.02f;
    break;

    case 'e':
    speed3 = 0.0f;
    break;
case 'f':
   speed3 = 0.03f;
    break;
    case 'g':
    speed4 = 0.0f;
    break;
case 'h':
    speed4 = 0.03f;
    break;

    case 'i':
    speed5 = 0.0f;
    break;
case 'j':
    speed5 = 0.025f;
    break;

    case 'k':
    speed6 = 0.0f;
    break;
case 'l':
    speed6 = 0.017f;
    break;



    case 'm':
    speed_3rd_car = 0.0f;
    break;
case 'n':
    speed_3rd_car = 0.02f;
    break;

    case 'o':
    speed8 = 0.0f;
    break;
case 'p':
    speed8 = 0.003f;
    break;
 case 'r':

    rainday=true;

        glutPostRedisplay();
    break;
case 'x':
  rainday=false;
        glutPostRedisplay();
    break;
case 's':
    flower=true;
        glutPostRedisplay();
    break;
case 'y':
  flower=false;
        glutPostRedisplay();
    break;
case 'w':


    snowday=true;
    glutPostRedisplay();

    break;
case 'z':

  snowday=false;
        glutPostRedisplay();
    break;







glutPostRedisplay();
}}







/* Main function: GLUT runs as a console application starting at main()  */
int main(int argc, char** argv)
{
   cout<<endl << "This project is created by : "  <<endl << endl;
   cout << "1.Marmita Paul"<< endl;
   cout <<"   "<<endl;
   cout <<"   "<<endl;
   cout <<"   "<<endl;
   cout <<"   "<<endl;
   cout <<"   "<<endl;

    cout <<endl<<   "                                  Project Name : Natural Beauty Of Village                    " <<endl<< endl;
    cout <<"   "<<endl;
    cout <<"   "<<endl;
    cout <<"   "<<endl;
    cout << "Press a : To stop cloud 1"  << endl;
    cout << "Press b : To move cloud 1"<< endl;
    cout <<"   "<<endl;
    cout << "Press c : To stop cloud 2"  << endl;
    cout << "Press d : To move cloud 2"<< endl;
    cout <<"   "<<endl;
    cout << "Press e : To stop the blue colors' birds"  << endl;
    cout << "Press f : To move the blue colors' birds"<< endl;
    cout <<"   "<<endl;
    cout << "Press g : To stop the light pink colors' birds"  << endl;
    cout << "Press h : To move the light pink colors' birds"<< endl;
    cout <<"   "<<endl;
    cout << "Press i : To stop the light blue colors' car"  << endl;
    cout << "Press j : To move the light blue colors' car"<< endl;
    cout <<"   "<<endl;
    cout << "Press k : To stop the pink colors' car"  << endl;
    cout << "Press l : To move the pink colors' car"<< endl;
    cout <<"   "<<endl;
    cout << "Press m : To stop the red colors' car"  << endl;
    cout << "Press n : To move the red  colors' car"<< endl;
    cout <<"   "<<endl;
    cout << "Press o : To stop the jackfruit colors' boat"  << endl;
    cout << "Press p : To move the jackfruit colors' boat"<< endl;
    cout <<"   "<<endl;
    cout << "Click mouse left : To increase speed all moving objects "  << endl;
    cout << "Click mouse right : To decrease speed all moving objects "<< endl;
    cout <<"   "<<endl;
    cout << "Press r : To start rainy season "  << endl;
    cout << "Press x : To stop rainy season "<< endl;
    cout <<"   "<<endl;
    cout << "Press w : To start winter season "  << endl;
    cout << "Press z : To stop winter season "<< endl;
    cout <<"   "<<endl;
    cout << "Press s : To start spring season "  << endl;
    cout << "Press y : To stop spring season "<< endl;
    cout <<"   "<<endl;

	glutInit(&argc, argv);                 // Initialize GLUT

    glutInitWindowPosition(0,0);
	glutInitWindowSize(1500, 770);
    glutCreateWindow("Natural Beauty Of Village"); // Create a window with the given title
	glutDisplayFunc(load_Start);
	glutTimerFunc(100, update_sun, 0);
	glutTimerFunc(100, update_moon, 0);
	glutTimerFunc(100, update1, 0);
   glutTimerFunc(100, update2, 0);
   glutTimerFunc(100, update3, 0);
    glutTimerFunc(100, update4, 0);
    glutTimerFunc(100, update5, 0);
   glutTimerFunc(100, update6, 0);
   glutTimerFunc(100, update_3rd_car, 0);
   glutTimerFunc(100, update8, 0);
   glutTimerFunc(100, update_rain, 0);
   glutTimerFunc(100, update_snow, 0);
   glutKeyboardFunc(handleKeypress);
   glutMouseFunc(handleMouse);


    glutIdleFunc(Idle);

	glutMainLoop();           // Enter the event-processing loop
	return 0;
}
