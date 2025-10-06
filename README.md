- WORKS FOR BLENDER v4.5+
- Use Grease Pencils's bottom layer keyframes to render
- Exported in "export" folder in the same path as your .blend file
- Limitations : - No Camera Data export
                - No Instanced Drawing/Duplicate Cell Number

ABOUT XDTS :
```
- 1 Field: Input location of each timesheet instruction. Fields are divided into cells, dialog, and
camerawork.
fieldId field name details
    0 - Cell - Field for cell numbers
    3 - Dialog - Field for speaker names and line timing
    5 - Camerawork - Field for camerawork instructions

- 2 Currently only supports instructions with id=0.
- 3 Values are different depending on the field type. Values for each field are as follows.
I Field name I value details                                                    I value element numbers I
I Cell       I Enter the cell number string and special instruction string(*4)  I 1                     I
I Dialog     I In the dialog's first frame, enter the speaker name in the       I 1～2
                first element, and the dialog's string in the second element.
                When the line lasts for multiple frames, specify the character
                string "SYMBOL_HYPHEN" up to the end frame.
I Camerawork I Enter the camerawork information in strings in the following
                order.

                1. Camerawork direction
                    ● Enter the camerawork direction with the string at the
                    first frame of the camerawork. In case the camerawork
                    continues between the number of frames, specify the
                    character string of "SYMBOL_HYPHEN" up to the end
                    frame.
                2. X coordinate value of camera position
                3. Y coordinate value of camera position
                4. Magnification percentage
                5. Rotation angle
                6. X coordinate value of camera center position
                7. Y coordinate value of camera center position

- 4 Special instruction character strings inside the "values":
    SYMBOL_TICK_1 -- Inbetween Symbol ○
    SYMBOL_TICK_2 -- Reverse Sheet Symbol  ● 
    SYMBOL_NULL_CELL -- Empty Cell x
    SYMBOL_HYPHEN -- Continue prev field instruction -

- 5 Set as 0 when specifying the first frame of the cell.

*6 Set as 0 for the bottom layer (trackNo).
    Specify layer names with trackNo's that match numbers counted as 0,1,2, etc.
    EX :  "fieldId": 0, "names": [ "A", "B" ] } # Layer A is "trackNo" : 0 , Layer B is "track no 1"

*7 Use SYMBOL_NULL_CELL in the values of the last frame EX: duration is 24 frame
```
