# URDF Creation

## 1 Masses & Inertia matrices in Solidworks

To get a part's mass properties do: `Tools > Evaluate > Mass Properties`. You will see the following image:

<img src="img/mass_properties.png" alt="Mass properties" align="center" width="500"/>

We have to select a the part to see its properties in the window. The selected part will appear in the top blue box. If we select an entire assembly (or multiple parts), the data will correspond as if all the parts form a single rigid body.

A good practice is to create a `Coordinate System` in the part and select it as a refernce in the dropdown list `Report coordinate values relative to:`.

The important fields in this image are the following:

- **Density**: Density of the part. Specified assigning a specific material to the part.
- **Mass**: Computed using the part's density and its volume.
- **Center of mass**: center of mass of the part. *Changes depending on the selected coordinate system.*
- **Moments of inertia, taken at the center of mass**: This is the inertia matrix at the center of mass of the part and aligned with the selected coordinate system. *Changes depending on the selected coordinate system.* **This matrix is the one used when exporting to a URDF**.
- **Moments of inertia, taken at the output coordinate system**: This is the inertia matrix at origin of the selected coordinate system and aligned with it.

> **INFO** :information_source: : The mass value can be overridden with the button placed at the top of the window `Override Mass Properties...` and the inertia matrices will be changed accordingl. :warning: *Please, note that the overridden mass is NOT considered when exporting to URDF**.

## Exporting to URDF

