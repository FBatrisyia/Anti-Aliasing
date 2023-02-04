#include <gl/glew.h>
#include <GLFW/glfw3.h>
#include <cstdlib>

#define window_width 600
#define window_height 400

GLFWwindow* glfw_window = NULL;


int main(void) {

    if (!glfwInit())
    {
        exit(EXIT_FAILURE);
    }

    glfwWindowHint(GLFW_SAMPLES, 5);

    glfw_window = glfwCreateWindow(window_width, window_height, "After Anti-Aliasing", NULL, NULL);

    if (!glfw_window) {
        glfwTerminate();
        exit(EXIT_FAILURE);
    }

    glfwMakeContextCurrent(glfw_window);

    glViewport(0.0f, 0.0f, window_width, window_height);

    glMatrixMode(GL_PROJECTION);

    glLoadIdentity();
    glOrtho(0, window_width, 0, window_height, 0, 1);
    glMatrixMode(GL_MODELVIEW);
    glLoadIdentity();

    GLfloat vertices[] =
    {
        250, 300, 0,
        100, 130, 0,
        400, 130, 0,
        450, 150, 0,
        440, 300, 0

    };

    glPolygonMode(GL_FRONT_AND_BACK, GL_FILL);

    while (!glfwWindowShouldClose(glfw_window)) {

        glClear(GL_COLOR_BUFFER_BIT);

        glEnableClientState(GL_VERTEX_ARRAY);
        glVertexPointer(3, GL_FLOAT, 0, vertices);
        glDrawArrays(GL_POLYGON, 0, 5);
        glDisableClientState(GL_VERTEX_ARRAY);

        glEnable(GL_MULTISAMPLE);

        glfwSwapBuffers(glfw_window);


        glfwPollEvents();

    }

    glfwTerminate();

    return 0;

}
