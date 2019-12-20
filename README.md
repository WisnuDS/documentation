# Documentation For Me
## Butterknife Android

    android {
      ...
      // Butterknife requires Java 8.
      compileOptions {
        sourceCompatibility JavaVersion.VERSION_1_8
        targetCompatibility JavaVersion.VERSION_1_8
      }
    }
    
    dependencies {
      implementation 'com.jakewharton:butterknife:10.2.1'
      annotationProcessor 'com.jakewharton:butterknife-compiler:10.2.1'
    }
## Glut/OpenGL
### CMake
    cmake_minimum_required(VERSION 3.10) # common to every CLion project
    project(OpenGLLinuxTest) # project name
    
    set(OpenGlLinkers -lglut -lGLU -lGL) # setting all the Glut libraries as one variable.

    ################################################
    
    add_executable(OpenGLLinuxTest1 main.cpp ) #common to all clion project
    
    target_link_libraries(OpenGLLinuxTest1 ${OpenGlLinkers}) # linking opengl libraries to the project
    
    #################################################

### Template
    #include <GL/gl.h>
    #include <GL/glu.h>
    #include <GL/glut.h>
    void displayMe(void){
	    glClear(GL_COLOR_BUFFER_BIT);
	    glBegin(GL_POLYGON);
	    glColor3b(250,100,0);
	    glVertex2f(1, 0.0);
		glVertex2f(0.0, 1);
		glVertex2f(0.0, 0.0);
    	glEnd();
    	glutSwapBuffers();
    }
    
    int main(int argc, char** argv){
		glutInit(&argc, argv);
		glutInitDisplayMode(GLUT_RGB | GLUT_DOUBLE);
		glutInitWindowSize(1368, 728);
		glutInitWindowPosition(0,0);
		glutCreateWindow("Hello world!");
		glutDisplayFunc(displayMe);
		gluOrtho2D(0, 5, 0, 5);
		glutMainLoop();
		return 0;
    }
