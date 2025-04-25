```
#include "raylib.h"
#define SIZE 32
int main(void)
{
    InitWindow(800, 600, "Drag to Draw Line");
    SetTargetFPS(60);

    Vector2 start = { 0, 0 };
    Vector2 end = { 0, 0 };
    bool drawing = false;

    while (!WindowShouldClose())
    {
        BeginDrawing();
        ClearBackground(RAYWHITE);

        if (IsMouseButtonPressed(MOUSE_LEFT_BUTTON))
        {
            start = GetMousePosition();
            drawing = true;
        }

        if (IsMouseButtonDown(MOUSE_LEFT_BUTTON))
        {
            end = GetMousePosition();
        }

        if (drawing)
        {
            DrawCircleV(start, SIZE/2, GREEN);
            DrawLineEx(start, end, SIZE, RED); // ✨ 선 굵기를 4픽셀로! (DrawLineEx 사용)
            DrawCircleV(end, SIZE/2, BLUE);
        }

        EndDrawing();
    }

    CloseWindow();
    return 0;
}
```
