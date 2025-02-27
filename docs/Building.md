
# Building

We use **Tauri** which requires ***[some extra setup]***.

## Sidecar

The interface uses **Sidecar** as it's backend for communication <br>
with **OpenVR** and must be built first for the project to run.

1. Navigate to `/sidecar/`.

2. **Create** & **Enter** a folder named `build`.

3. Run CMake with:

    ```sh
    cmake ..
    ```

4. Open the generated **Visual Studio** project.

5. **Build** the project in a `Release` / `MinSizeRel` mode.

6. Copy the build **Artifacts** into `/src-tauri/`.
    - `sidecar-x86_64-pc-windows-msvc.exe`
    - `openvr_api.dll`

<br>

## Building the Application

1. Have **[Sidecar]** built.

2. Install dependencies with:

    ```sh
    yarn install
    ```

3. Launch the development server with:

    ```sh
    yarn run dev
    ```

    *The initial run may take a significant amount of time.*

4. Build the interface with:

    ```sh
    yarn run build
    ```

    ***Artifacts*** *will be placed in `src-tauri/targets/release`.* <br>
    *An* ***Installer*** *is located in `src-tauri/targets/release/bundle-msi`*

<br>

##### Note

Using the **Installer** will automatically install `Webview2`.

If you only plan on distributing the **UI** & **Sidecar** <br>
binaries, you will have to manually install [`Webview2`].


<!----------------------------------------------------------------------------->

[Sidecar]: #Sidecar

[some extra setup]: https://tauri.studio/en/docs/get-started/intro
[`Webview2`]: https://developer.microsoft.com/en-us/microsoft-edge/webview2/#download-section
