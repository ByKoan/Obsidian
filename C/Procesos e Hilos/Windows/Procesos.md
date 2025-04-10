***Una aplicacion consta de uno o varios procesos. Un proceso es un programa o instancia en ejecución, uno o varios subprocesos se ejecutan en el contexto del proceso (Unidad básica a la que el sistema operativo asigna tiempo de procesador). Un subproceso puede ejecutar cualquier parte del código, incluido los elementos que esta ejecutando actualmente otro subproceso***

### Creación de procesos:

- ***En Windows tenemos la funcion `CreateProcess()`, crea un nuevo proceso que se ejecuta independientemente del proceso de creación. (Necesitamos la header `<windows.h>`)

```c
#include <windows.h>
#include <stdio.h>

char exe_path[] = "C:\\Windows\\system32\\notepad.exe";
STARTUPINFO startup_info;
PROCESS_INFORMATION process_info;

BOOL process_status = FALSE;

// allocate memory and clear memory
ZeroMemory(&startup_info, sizeof(startup_info));
startup_info.cb = sizeof(startup_info);
ZeroMemory(&process_info, sizeof(process_info));

process_status = CreateProcess(
    NULL,           // Use the command line arg instead
    exe_path,       // path to exe using command line
    NULL,           // Process handle not inheritable
    NULL,           // Thread handle not inheritable
    FALSE,          // Set handle inheritance to FALSE
    0,              // No creation flags
    NULL,           // Use parent's environment block
    NULL,           // Use parent's starting directory
    &startup_info,  // Pointer to STARTUPINFO structure
    &process_info); // Pointer to PROCESS_INFORMATION structure

/* Do work with handles */

// Close process handles and clean up
CloseHandle(process_info.hProcess);
CloseHandle(process_info.hThread);
```