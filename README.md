
 //Programmer: Miles Natividad

#include <GL/glut.h>
		
		void display();
		void reshape(int,int);
		void timer(int);
		
		void init()
		{
		glClearColor(0.0f, 0.0f, 0.0f, 0.0f);
		glEnable(GL_DEPTH_TEST);
		
		}
		
		int main(int argc,char**argv)
		{
		glutInit(&argc,argv);
		glutInitDisplayMode(GLUT_RGB | GLUT_DOUBLE | GLUT_DEPTH);
		glutInitDisplayMode(GLUT_RGB);
		
		glutInitWindowPosition(100,100);
		glutInitWindowSize(900,1000);
		glutCreateWindow("MILES NATIVIDAD");
		
		
		glutDisplayFunc(display);
		glutReshapeFunc(reshape);
		glutTimerFunc(0,timer,0);
		init();
		
		glutMainLoop();
		}
		
		
		void display()
		{
		
		
		glClear(GL_COLOR_BUFFER_BIT | GL_DEPTH_BUFFER_BIT);
		glLoadIdentity();

			
		glTranslatef(0.0f,0.0f,-8.0);
		
		glBegin(GL_QUADS);

	glColor3f(1.0,0.0,0.0);
	glVertex2f(-8.0,0.0);
	glVertex2f(-8.0,-10.0);
	glVertex2f(-7.0,-10.0);
	glVertex2f(-7.0,0.0);

	glColor3f(1.0,0.0,0.0);
	glVertex2f(-7.0,-1.0);
	glVertex2f(-4.0,-5.0);
	glVertex2f(-4.0,-4.0);
	glVertex2f(-7.0,0.0);

	glColor3f(1.0,0.0,0.0);
	glVertex2f(-4.0,-4.0);
	glVertex2f(-4.0,-5.0);
	glVertex2f(0.0,0.0);
	glVertex2f(-1.0,0.0);

	glColor3f(1.0,0.0,0.0);
	glVertex2f(-1.0,0.0);
	glVertex2f(-1.0,-10.0);
	glVertex2f(0.0,-10.0);
	glVertex2f(0.0,0.0);

	glColor3f(0.0,1.0,0.0);
	glVertex2f(2.0,0.0);
	glVertex2f(2.0,-10.0);
	glVertex2f(3.0,-10.0);
	glVertex2f(3.0,0.0);

	glColor3f(0.0,1.0,0.0);
	glVertex2f(3.0,-1.0);
	glVertex2f(8.0,-10.0);
	glVertex2f(9.0,-10.0);
	glVertex2f(3.0,0.0);

	glColor3f(0.0,1.0,0.0);
	glVertex2f(8.0,0.0);
	glVertex2f(8.0,-10.0);
	glVertex2f(9.0,-10.0);
	glVertex2f(9.0,0.0);

	glEnd();

	glutSwapBuffers();
}
		
	     void reshape(int w, int h)
		{
		glViewport(0,0, (GLsizei)w, (GLsizei)h);
		glMatrixMode(GL_PROJECTION);
		glLoadIdentity();
		gluPerspective(150,1,2.0,100.0);
		glMatrixMode(GL_MODELVIEW);
		
		}
		
		void timer(int)
		{
		glutPostRedisplay();
		glutTimerFunc(1000/60,timer,0);
		
		}
