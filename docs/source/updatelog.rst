UPDATES LOG
===========

.. autosummary::
   :toctree: generated
   
   
.. _3590:

v3.59 - 2022/07/30
-------------------

**SMONSTER**
• Code Optimization  and Command naming harmonization.

**CAD**
• Bugfix on Training Scene - Rebuild Radial (duplicated vertex causing issue for users while testing the commands).

**BAKE**
• Exposed the CreatePairsFromHighPolyMesh command in UI pop over menu as well as in Item Context Menu (right click).

**GC**
• Changed smo.GC.AffinitySVGRebuild Cmd to smo.GC.SplitByPolySelectionSet as it as a general usage.
• Exposed smo.GC.SplitByPolySelectionSet in SMONSTER / Top Menu.
• smo.GC.IsolateItemAndInstances Cmd now select automatically the source mesh in the item list even if you launched it while having an instance selected.
• smo.GC.IsolateItemAndInstances is now also exposed in Viewport Context Menu (right click).
• Setup cmd Move Center to selection now also works in item Mode (it will move the center item at the center of the mesh layer).



.. _3550:

v3.55 - 2022/07/18
-------------------

**SMONSTER**

• Training Scene Menu switched to Vertical toolbar.

**GC**

• Added warning if you try to use commands that use Modollama kit without getting it activated / loaded.
• Bugfix forms for users that got already Seneca SuperTaut function and forms in their keymapping.

**UV**

• UV Tools Menu Reordering



.. _3500:

v3.50 - 2022/06/20
-------------------

**GC**

• Update on FBX Preset Pop Up Menu to expose more options.
• New Command --> smo.GC.ConvertToHardEdgeWorkflowUsingGeoBoundaryAsHardEdge (On current Mesh item, convert Shading Method to HardEdge Workflow using geometry boundary as "HardEdge" and set all other Edges as "Smooth".)
• New Command --> smo.GC.ExportMeshAsMeshPreset (Export current Mesh As MeshPreset LXL file into Target Path. (optional: Define Path destination as argument))
• New Command --> smo.GC.ExportSelectedMeshesAsMeshPreset (Export Selected Meshes As MeshPreset LXL file into Target Path. (optional: Define Path destination as argument))
• New Command --> smo.GC.CreateEmptyChildMeshMatchTransform (Create a new child Mesh Item (empty) on current selected mesh item.)
• New commands for MicroBevel Workflow:

  • New Command --> smo.GC.SimplifyToNGon & smo.GC.MultiSimplifyToNGon (Merge every polygons that have same coplanar polygon direction to simplify a given set of meshes. Via argument you can also update the HardEdges data for a better end result.)
  • New Command --> smo.GC.MicroBevelHardEdgesAndUpdateToSoften & smo.GC.MultiMicroBevelHardEdgesAndUpdateToSoften (Micro Bevel HardEdges (usually after a SimplyToNgon), then Soften all edges.)
  • New Command --> smo.GC.ModollamaRebuildNGontoTriangle & smo.GC.MultiModollamaRebuildNGontoTriangle (Rebuild all NGons via Modollama Triangulation command to output Triangles.)
  
• Bugfix on smo.GC.RenderThumbPreset

**CLEANUP**

• PopUp menu updated
• New Command --> smo.CLEANUP.ConvertAllSolidWorksShape (Search for all Solidworks Shape Items in the scene and convert them to regular Meshes. Delete the empty meshes in the process as well.)
• New Command --> smo.CLEANUP.CleanupSolidWorksImport (Cleanup SolidWorks Import (from McMaster Website Data) in order to save a new scene with only one Mesh item of the imported asset. It will also convert the VertexNormals Data to HardEdgeWorkflow if needed.)
• New Command --> smo.CLEANUP.DelEverythingExceptMeshes (Select everything in the current scene, except Meshes items and delete all other items / materials. It unparent in place the current Meshes to preserve their position in space in case they were part of a hierarchy.)
• New Command --> smo.CLEANUP.RemoveAllPartTags (Check for all Meshes in the current scene remove any part tags in it.)
• New Command --> smo.CLEANUP.DelPreTransform (Freeze Scale transform of all meshes in scene but if there is instances, it retain Instances scale to 100 percent or -100 percent as well.)
• Bugfix smo.CLEANUP.RenameUVMapToDefaultSceneWise (That command now create an empty UV map if one is missing using Default UVMap name from Preferences)

**BATCH**

• PopUp menu updated
• Support for SLDPRT added as Input file format (CAD file - Solidworks)

**UV**

• Menu and Icons (Big UI refresh)
• Bugfix (Get UVMap Count argument not correctly exposed. It adds also a 4th argument to deselect all maps except UV maps)



.. _320:

v3.20 - 2022/05/10
-------------------

**GC**

• Fixed an issue with Error message populating the Event Log, while using the smo.GC.SetNewMaterialSmartRename command as well as the Quick Tag - Set Mat Color ID commands.
• (Remap the SMO GAME CONTENT MainKeymaps as the smo.GC.SetNewMaterialSmartRename now need a Boolean Argument at the end. --> "smo.GC.SetNewMaterialSmartRename 1" to show Modo Color Picker at launch)

**QUICK TAG**

• Solved a regression with latest update on Batch - Set Mat Color ID commands
• If the Color ID command is used while in Item Mode, it will switch back to item mode, after running it.

**CLEANUP**

• Added Rename Vertex Normal Map by Modo Default name for imported FBX files --> ( FBX_normals)
• Changed the Popup menu UI layout for better functions discoverability



.. _315:

v3.15 - 2022/04/29
-------------------

**RIZOMUV Livelink**

• MODO 16.0v1 Support

**QUICK TAG**

• New Command --> smo.QT.SetMatColorIDByMeshIslands (Set Color ID by Material Tag, by Polygons Continuity (Islands) on current mesh.)
• New Command --> smo.QT.Batch.SetMatColorIDRandom (Set Color ID by Material Tag, by Polygons Continuity (Islands) over multiple MeshLayers or Scene wide.)
• Bugfix on smo.QT.SetMatColorIDRandom / smo.QT.SetMatColorIDByUser / smo.QT.SetMatColorIDByNumber.



.. _310:

v3.10 - 2022/04/28
-------------------
**GC**

• New Command --> smo.GC.SplitByPart
• New Command --> smo.GC.SplitByMaterial
• New Command --> smo.GC.PlasticityPrepareMeshes (Command to preprocess data from OBJ import from Plasticity. Cleanup Meshes data from Plasticity creating Polygons Parts, Unwraped UVMaps and Merging Solid items.)
• Bugfix on smo.GC.EdgeSlideProjectToBG command that wasn't releasing the EdgeSlide tool at the end of his execution.
• Bugfix Switching to AVP Shading Style (The view should now not be offset or reset in terms of Point of view).

**QUICK TAG**

• Introduced functions to process the color ID attribution Scene Wide and / or even By Mesh Islands (Polygon Continuity)
• New Command --> smo.QT.Batch.SetSelSetColorIDRandomConstant (Set a random Diffuse Color override using Selection Set (polygons) and Constant item. It can runs over Selected Meshes or SceneWide, By Items or by Polygon Islands.)
• New Command --> smo.QT.SetSelSetColorIDByMeshIslands (Set a Diffuse Color override using Selection Set (polygons) on the selected Mesh Layers by Polygons Continuity (Islands). Named the new Mat using "ColorID" as Prefix.)
• Bugfix on the main command that where not processing the data correctly with specific user scene behavior.

**UV**

• Bugfix on UnwrapCylindrical to disable Auto RelaxUV Island if the Unwrap Rectangle was True and AutoRelax was True, in order to keep Rectangle result in output.



.. _3000:

v3.00 - 2022/03/03
-------------------

• Initial Commit to New Release V3.
• It now support Modo 15.0 to 16.X releases with 100% Compatibility.
• All further developments will focus on support from Modo 15.0v1 to 16.X.
• You're free to load it on earlier releases of Modo (from 14.0), but i won't provide any bugfix on earlier release of Modo than 15.0v1 from 2022 March 2th in order to get my focus on Future plans for Modo 16.X series.

**GAME CONTENT**

• New Command --> EdgeBoundarySimpleFuse to fuse (without Projection) an Open Edge Boundary loop ( V Norm data is kept from BG Mesh of set Self if mouse over empty area in viewport).
• New Command --> SplitUDIMtoMesh to separate a mesh based on UDIM Polygons layout. It create New Mesh Layers, using target Mesh Name, PrefixName, UDIM ID from current selected Mesh.
• Bugfixes on EdgeBoundaryProjectToBGnFuse to support Self Project onto same mesh. Also hiding other meshes for TransferVNData automatically
• Transfer VNorm from BG Mesh now have an option to "Lock" edited component when the command is used. Toggle is set to off by default. It is located in the GC Options under Modo Preferences Window.
• Layout change in right click Context Menus to add more options and commands.

**RIZOMUV Livelink**

• MODO 15.2v2 Support
• RizomUV 2022.0 Support
• Bugfix for those who also are using Vertex Normals maps in their workflow. In any case the kit won't update in Modo you could still open the Temp FBX File in order to get back all the data from Materials to VNrm to UV's of course.



.. _2756:

v2.756 - 2022/01/28
-------------------

**MIFABOMA**

• Improvement and Bugfix on RADIAL ARRAY and MIRROR commands that now support:
  • Both Meshes and MeshInstances (instead of only regular Meshes only).
  • Multiple Items selected at once. They will now process duplication over multiple selected items as intended.



.. _2755:

v2.755 - 2022/01/21
-------------------

**QUICK TAG**

• New Command

  • Set ColorID (by SelectionSet and Constant item override) ---> For ColorID Bakes from LowPoly.
  
    • --> That system doesn't mess up the Material attribution and only add modification via Constant item override and Poly SelectionSet.
    • --> Those resulting Meshes can be exported as FBX and Retain Color in Diffuse.
    • --> ColorID tags are unique Scenewise and MeshWise, so now you can't have one polygon that share more than one ColorID. It prevent layout issue in Shader Tree.
  
  • Set ColorID (by Material Tags) ---> For ColorID Bakes from HighPoly.
  
    • --> Usually outside of Modo, like in Substance Painter or Marmoset Toolbag.
    • --> Those resulting Meshes can be exported as FBX and Retain Color in Diffuse.

• You can recall any existing Color ID you create to override existing one, via a Gang Menu of 17 Color ID Presets (from 0 to 16)
• You can assign any existing Color ID by a User input value in a Pop window. 
• Thanks to user feedback, i've set the first 0 to 16 ColorID with ItemColorCoding inside the ShaderTree, as well as fixed colors.
• Passed ID #16, it will create random Color each time you create a new one.

**GAME CONTENT**

• New smo.GC.UDIMtoMaterial command to convert a Unique Material assignation to a set of Multiple Materials tag, for easy export of UDIM ready Meshes (created via Substance Painter for instance) to Unity Engine.
  • This command use this argument setup: smo.GC.UDIMtoMaterial {Material Name} {UDIM Start ID} {UDIM END ID}
  • Polygon and Edge (right click) Context Menu now have a Chamfer by User Value command for custom size.



.. _2737:

v2.737 - 2022/01/05
-------------------

**GAME CONTENT**

• TransferVNrmFromPolyUnderMouse command added to Context Menus, in order to Transfer Vertex Normals from the Mesh under the mouse to the corresponding selected components (Vertex / Edges / Polygons)

.. note::

   It works both on multiple meshes condition as well as self mesh transfer.



.. _2730:

v2.730 - 2021/12/20
-------------------

**GAME CONTENT**

• EdgeboundaryProjectNFuse Bugfix.

**VENOM**

• Added a toggle for Switching or not in Isolate Mode in Tail Menu and Preferences



.. _2726:

v2.726 - 2021/12/15
-------------------

**GAME CONTENT**

• Added more Chamfer presets to Polygon Context Menu
• Bugfix on MiniProperties Keymap assignment on Shift-Space (via the Menu SMONSTER / Quick Keymaps / GameContent - Modo15.1 Remapping Cmd). Now it should show up the popover as expected.

**COLOR BAR**

• Added the Locator Shape Menu to Tail Menu
• Added a toggle to enable Disable Independent Drawing in current viewport to all Color Bar Menus



.. _2724:

v2.724 - 2021/12/14
-------------------

**GAME CONTENT**

• BugFix on StraightenEdgeBoundary on specific condition
• Exposed the ability to Transfer Vertex Normal Data via Toggle in GC Preferences (while using the EdgeBoundaryProjectNFuse)



.. _2722:

v2.722 - 2021/12/08
-------------------

**GAME CONTENT**

• Added 3 new commands to Edge Context Menu

  • smo.GC.StraightenEdgeBoundary: It flatten the selected Edge Boundary to fix squeezed profile.
  • smo.GC.FixVertexWithNullVNormData. It fix missing VertexNormals on a given mesh.
  • smo.GC.EdgeBoundaryProjectToBGnFuse. It extend the current Opened Boundary Edge Loop to nearest BG Mesh using BG Constraint. Then it inset out the resulting Polygon and Edge Bevel it + applying a VertexNormalTransfer to fuse the border with BG Mesh normals.
  
• smo.GC.ChamferEdgeByUnit count is now exposed in the Preferences tab. it affect as wel the smo.GC.EdgeBoundaryProjectToBGnFuse accordingly.

**VENOM**

• Exposed the Show / Hide VNormal Vectors in the Tail Menu as well as in preferences.



.. _2710:

v2.710 - 2021/11/28
-------------------

**BATCH**

• Bugfix on Opening SVG/DXF/FBX/LXO Files that was Empty. Causing Batch script to stop as there was no data to treat. (Load SVG/DXF/FBX/LXO) Now it's removing files that are empty from the conversion filepath list.

**GAME CONTENT**

• Bugfix Missing Environment for Render Preset Thumbnails.
• Addition of more commands in context menus Polygon and Vertex for Vertex Normals

**VENOM**

• Bugfix to keep current item selection when in Item Mode after launching the main command.



.. _2700:

v2.700 - 2021/11/15
-------------------

**GAME CONTENT**

• Added Edge UnbevelRing command (default hotkey set to Ctrl-Shift-U)
• Now there's also an option to use Original Modo Material command via a Toggle for SmartMaterial command.
• Bugfix on SmartMaterial that was returning error in Modo 15.2 for Area Weighting method.
• Bugfix on Render Thumbnail Scene (in case meshes Maximum Sizes was 1m / 0.1m / 0.01m / 0.001 )



.. _2694:

v2.694 - 2021/11/10
-------------------

**GAME CONTENT**

• Bugfix on Batch Mesh Preset to take care of the item center on thumbnail rendering.
• Bugfix on Thumbnail Render template scene.



.. _2692:

v2.692 - 2021/11/08
-------------------

**SMONSTER**

• Batch Export to LXL Mesh Preset command added to Smonster Top menu.

**GAME CONTENT**

• Batch convert all the Meshes in the scene to Mesh Preset with custom Thumbnail automatic render.
• Convert selected Mesh to Mesh Preset with custom Thumbnail automatic render.
• Subfolder function for this command Specific folder or SMO GC Kit folder.
• Customizable Background Color for this command.
• Command to Create / Remove Subfolder Tag in scene



.. _2683:

v2.683 - 2021/10/26
-------------------

**SMONSTER**

• Bugfix on Unbevel Assignation to Ctrl + U in QuickKeymap commands.

**VENOM**

• Added the Transfer Vertex Normal from BG Mesh into the Main Pie Menu.



.. _2680:

v2.680 - 2021/10/22
-------------------

**GAME CONTENT**

• PieSwitcher pie menu added for Viewport Borders management.
• smo.Cleanup.RenameUVMapToDefaultSceneWise added (Check for all Meshes in the current scene and rename their First UVMap (by Index = 0) to Modo/Preferences/Defaults/Application name.)
• Bugfix on OpenTrainingScene Command and Forms.
• Bugfix Forms for Keymapping in GC Kit.
• Bugfix on FullscreenMode command.

**BATCH**

• Added Support for All exposed Inputs and Outputs.
• Bugfix on OBJ to OBJ and OBJ to FBX.
• Added New Preset to Reset Center of Meshes OBJ and convert then to FBX.



.. _2674:

v2.674 - 2021/10/19
-------------------

**SMONSTER**

• Documentation WebLinks and Dedicated Menu are stored as a unique Kit now. --> SMO_DOC

**DOC**

• Update on Documentation.
• New Command to open Youtube Video links using User preferences (Resolution)

**BATCH**

• Added an Option in Preferences to Convert All Meshes Item to Static Meshes when Ouputing Data to LXO File.

**GAME CONTENT**

• smo.GC.SetNewMaterialSmartRename

  • Create a New Material Tag
  • Rename the Material Layer in Shader Tree according to Group Material name with a Suffix (suffix defined in Prefs, as well as Separator based on Modo Index Style Prefs).
  • Set the Shading Model via Preferences / SMO GC Options (Traditionnal, Energy Conserving, Physical Based, Principled, Unreal, Unity, glTF, AxF)
  • Color Constant Override for Unreal, Unity, glTF, AxF to get correct color in Viewport (if needed via option)
  • This command is assigned to "M" Key (via a oneclick form).

• Meshops Popup form is now filtering available Meshops relative to your current Selection type (Vertex / Edge / Polygon / Item)
• Finaly exposed that new Command: smo.GC.Setup.OffsetCenterPosPreserveInstancesPos that let you redifine Center Position on selected Mesh Item, but preserve the Instances Positions in Worldspace. (Useful for CAD)
• Rewrite the Add Meshop Command to automatically arrange nodes when created.
• Updated the AVP Game viewport Preset (Independent  Rotation, Position and Scale are now enabled).
• Bugfix for QuickCreateCameraMatcherScene to not be Case Sensitive (both .jpg and .JPG are now supported).
• AVP Game viewport Preset are now loaded according to yourModo Version. It will solve issue with post 15.0 Presets.
• AVP Game viewport Preset is now set to Progressive Antialiasing by default via Numpad 6 Key. 

**VENOM**

• Bugfix when working on meshes that was having more than one Rotation Transform items (FBX coming from other package like 3DSMax or Blender for instance)
• Bugfix That now allows to Update/Overwrite existing Vertex Normal Data.
• Bugfix to let User define their own VMap name.
    
**MIFABOMA**

• Bugfix for Mirror Tool in Polygon Mode under Modo 15.1 and up. (Invert Polygons option have opposite behavior now)
    
**CAD**

• Added Option for Rebuild Polystrip to work on Circle (Closed Loop). (using 2nd argument to define if it's working for a closed Polystrip)

**RIZOMUV LIVELINK**

• Addition of Pixel Margin / Spacing Mode On in Rizom UV Preferences Script.



.. _2635:

v2.635 - 2021/07/24
-------------------

**SMONSTER**

• Addition of adedicated full screen palette for Meshopsworkflow within schematic.
• Various little bugfix in forms / tooltip / menus.



.. _2626:

v2.626 - 2021/07/18
-------------------

**MARMOSET TOOLBAG LIVELINK**

• Added option to Auto bake AOF (Floor) map (only available in Marmoset Toolbag 4.03)
• Added option to define AO/Thickness RaySample count in preferences "Bake settings" --> (128 , 256, 512, 1024, 2048)
• Added option to define PerPixelSampling count in preferences "Bake settings" --> (1X , 4X, 16X)
• Maps list completely driven by Preferences in Modo to save out unwanted maps to be written in bake folder.

**RIZOMUV LIVELINK**

• Added support for material at Livelink Export to let you use materials for fast polygon selection in RizomUV

**UV**

• UV Kit now support Micro Bevel Workflow by letting you use Auto Expand Option on SmartUnwrap and PlanarUnwrap
• Added 2 Toggles to Main UV Pie menu to switch Auto Hide Unwrapped Poly and Auto Expand Poly



.. _2610:

v2.610 - 2021/06/25
-------------------

**SMONSTER**

• Rewrite the Remapping Information in all KeymapCommander Remapping Dialog.

**GAME CONTENT**

• Modo 15.1 KeymapCommander added to set back Original Modo behavior, even if new features like Mini-Properties have been added.

  • Global and Item Mode -> C = Channel Haul
  • view3DOverlay3D and Component Mode -> C = Edge Knife
  • view3DOverlay3D and Component Mode -> Shift-C = Poly Knife
  • view3DOverlay3D and Component Mode -> Alt-C = Poly Loop Slice
  • Global and ContextLess -> SpaceBar = Original Modo Behavior
  • Global and ContextLess -> Shift-SpaceBar = Mini-Properties Popover
• Set the Copy/Paste PieMenu remapping to Main Remapping (will appear only in ComponentMode via Ctrl + Shift + C)
• smo.QuickCreateCameraMatchSetup command added. (to set up Camera Match from a set of JPG Images (found in defined Folder)



.. _2600:

v2.600 - 2021/06/16
-------------------

**SMONSTER**

• Saved Edge Knife Remapping for further use in coming Modo 15.1.	C Key in Conmponent Mode
• Saved Channel Haul Remapping for further use in coming Modo 15.1.	G key in global Mode
• Added Preferences Settings for Meshops Deferred Evaluation.

**MESHOPS**

• Set back the Polyfuse 2D Meshop assembly Aliases to Meshops Presets V2.

**UV**

• Added "Select Coplanar Touching 2 Deg + Expand" in Pie Menu Form (for Mid Poly UV Mapping) 
• Adding "Select Coplanar on Object + Expand" in Pie Menu Form
• Bugfix on Smart Unwrap , when Edge Mode was used, the script wasn't repositioning the UVs in 0-1 Space when "Auto Relocate" option was False
• Bugfix on UnwrapCylindrical that now use Auto Relax and Auto Orient
• Bugfix in forms (tooltips)



.. _2600:

v2.590 - 2021/06/07
-------------------

**SMONSTER**

• General Bugfix in XML data  (Config files)
• Saved Spacebar remapping for furher use in coming Modo 15.1.

**MIFABOMA**

• Bugfix on forms Pie Menu. Mirror commands "Relative to Parent / Merge" and "Relative To Parent" was inverted. 
• Bugfix on Mirror commands to Support ReferenceSystem as well as update on VertexNormalMap at once.
• Bugfix on FlipOnAxis that now also support VertexNormalMap (they update correctly now) when you was using Reference System.

**GAME CONTENT**

• smo.GC.FlipVertexNormalData command added



.. _2583:

v2.583 - 2021/06/03
-------------------

**GAME CONTENT**

• smo.GC.Unbevel Command added.
• smo.GC.Setup.MoveRotateCenterToSelection Command added with 3 Modes Supported.
• smo.GC.MOD.MeshCleanup Command added.
• smo.GC.MOD.MeshCleanup with Optional Merge/Triple (that Remove Colinear Vertex mode, useful on Text characters).
• Added Select CoPlanar Menu to SMO GC PM (Pie Menu) and VM (vertical Menu) --> Select Section
• CENTER related Scripts are now Wrapped commands and they support Reference System state.
• Updated all the CENTERS Forms.
• AVP_GAME Shading Preset (Reduced the Wireframe Opacity back to 50% as it was too contrasted at 100 / 70 %).



.. _2575:

v2.575 - 2021/06/02
---------------------

**UV**

• Bugfix on path to UVGridChecker Command

**CAD**

• Bugfix to get the focus on Mesh Source if there is only one displayed in Isolate Mode (instead of fiting the viewport on both Instances and Source Meshes).
• BugFix Missing Icons on Merge CoPlanarPoly Pie Menu.



.. _2571:

v2.571 - 2021/05/31
-------------------

**CAD**

• Added CAD Fix Rotation Transform Order Cmd to convert all Rotation Transforms from "n" order to XYZ Order without loosing the item Position / Rotation in space.
• MergeCoplanar Poly Forms in Context Menu.
• Bugfix on CAD IsolateItemAndInstances. Now works in all conditions (From Selected (Meshes) or (Meshes + Instances) or (Instances)).

**GAME CONTENT**

• Added a "set VertexNormal" Command in Item / Viewport Context Menu.
• Added Unbevel Ring by Convergence Script in Edge Context Menu.
• Changed Color Scheme of Workplane color on SMO 3D ColorScheme preset.



.. _2565:

v2.565 - 2021/05/26
-------------------

**SMONSTER**

• Right Click Context Menu now have more sub-commands Filtered for each component mode:
  • MIFABOMA Commands
  • Merge Vertex (by distance preset)
  • Edge Collapse
  • Modollama Triple (by iterations count preset)
• Addition of Context Menu in Viewport Context Menu (Right click in viewport empty space).

**CAD**

• RebuildWithCylinder Side Count by User was added in the Pie Menus (via Axes Icons).
• Rebevel now support Reference System.
• Rebevel Bugfix when Meshes that got triangle Poly in the surrounding area around The processed selection.
• Smart Rebuild With Cylinder Added for better shape handling (Regular Radius Support).  (RebuildWithCylinder command have been removed).
• Copy / Cut to Child Mesh command Rework with Select Coplanar Modes and dedicated Pie Menu / Icons

**GAME CONTENT**

• MoveRotateCenter wrapped command added that wasn't supporting ReferenceSystem.
• Fullscreen ToggleCommand added.
    
**MIFABOMA**

• Bugfix on Radial Array with World Mode in Component Mode.
• Bugfix on Mirror that wasn't saving user settings.
• FlipOnAxis now support VertexNormalMap and update it.



.. _2542:

v2.542 - 2021/05/18
-------------------

**CAD**

• Bugfix on Rebevel.
• Rebevel / RebuildPolystrip now support Item Auto Selection in Component Mode (if you wasn't selecting the mesh before it will select it for you).



.. _2540:

v2.540 - 2021/05/17
-------------------

**SMONSTER**

• Added Item / Poly / Edge / Vertex - Right Click Context Menu with Smonster Commands 

**MIFABOMA**

• Boolean command is now preserving the current visible Items in the viewport when run.

**RIZOMUV LIVELINK**

• Bugfix: In case you wasn't exporting Meshes fully triangulated, MODO 15.0vx wasn't getting proper UV data as it was exporting the mesh triangulated instead of preserving the Mesh Topology (Square and Ngons).

**CAD**

• New Command: Rebuild Closed Polystrip.
• New Command: CopySelectionAsChildOfCurrentMesh.
• New Command: Merge CoPlanarPoly to replace old system on "Delete In... menu".
• RebuildWithCube and RebuildWithCylinder Open / Closed / Hole script now support Reference System workflow.
• RebuildWithCube and RebuildWithCylinder Open / Closed / Hole now support Item Auto Selection in Component Mode (if you wasn't selecting the mesh before it will select it for you).
• Rebevel / RebuildWithCylinder / RebuildWithCube are now Wrapped Commands.
• MergeCoplanarPoly Update on Forms.
• Bugfix: Rebevel was lefting over an edge selection set, now it doesn't left over things (leading to better compatibility).
• Bugfix: Delete Selection Set Item for RebuildPolyStrip / RebuildCylinder / Rebevel (Clear Tag).

**UV**

• Load custom UV Checker texture was added to the Smart Projection PieMenu (Different resolution available: 512px, 1024, 2048, 4096).

**GAME CONTENT**

• Hard Chamfer Presets to Edge Right Click Context Menu.
• Added PrimGenCylinder Commands. (create a new mesh, and create a cylinder with defined arguments)
• Disabled Split By Material from GC Pie Menu, to solve unwanted computation. now it's available from the Vertical Menu. (ctrl- shift- q)
• Bugfix on forms (Vertical Menu Update).

**CLEANUP**

• Added Rename All Instance by Source Mesh Name command.



.. _2510:

v2.510 - 2021/05/04
-------------------

**SMONSTER**

• CAD / GAME CONTENT / MIFABOMA / CLEANUP got some Bugfix when user was using their own Copy / Paste / Deselect mode in preferences.

**MIFABOMA**

• RADIAL SWEEP (Local) - Process from High Poly Option added (to Rebuild topology from HighPolyMesh Data. Require Edges profile selection and Polygons area to be removed in the process).
• Added the Preferences link on top of Tail Menu Pop Over.
• Bugfix on Booleans (that left unwanted Polygon Selection Sets after using the command).

**GAME CONTENT**

• UnbevelPolyLoop rewriten (ctrl-k and ctrl-shift-k commands).
• Bugfix: Remapping.
• Bugfix: StarTriple now works again on multiple selected islands, like it was expected to do.
• Bugfix: SelectCoplanar Poly.



.. _2502:

v2.502 - 2021/04/30
-------------------

**SMONSTER**

• Global BugFix on Delete command in Modo (that was asking for confirmation to delete Items / Component. (updated on Macro and Scripts))
• Switched CAD Tools / UV / VeNom Kits from Lazy Select (Seneca Menard scripts) workflow to Built-in Select CoPlanar Polygons command Introduced in recent release of Modo.
  • Better Performance in mentioned Kits.
  • No More headache on Initialize CAD / UV / Venom kit procedure. (Runs smoothly right after the installation.)

**VENOM**

• BugFix to support meshes with rotations (different than 0, 0 ,0). Local Space supported over World Space.

**MIFABOMA**

• Reference System Support (when it is defined on current Item in Local Mode and Component Mode)
• Item Auto Selection in Component Mode (if you wasn't selecting the mesh before it will select it for you).
  • Mirror
  • Slice
  • Radial Array
  • Booleans
  • Radial Sweep
  • Flip On Axis

**GAME CONTENT**

• New command added via Right Click Item Context Menu:
  • SMO GC SoloInstanceInPlace (Now select back the original Item instead of the Instance)
  • New SMO GC ReleaseFromIsolate
• Select Menu form updated to use the new Select CoPlanar Polys command

**CAD**

• Star Triple Flat (Reference System Support)
• Rebuild Radial Flat (Reference System Support)
• Rebuild Radial Tube (Reference System Support)

**BAKE**

• New Options for Create Bake Pairs from HighPoly Mesh
  • Create or Transfer VertexNormalMap from HighPoly to LowPoly
  • Activate the Reference System on LowPoly
  • Isolate current Bake Pairs in Viewport
• Updated the Pop Over Menu to expose more options that was previously visible only via Preferences

**UV**

• Unwrap Smart / Planar / Cylindrical commands (Reference System Support)
• Added the link to UV Preferences in Tail Menu.
• Bugfix on UV tools (Unwrap tools). (In case you wasn't selecting the Item first and worked directly in Polygon Mode. (Now he commands automatically select it for you at least if you have one Polygon Selected.)



.. _2473:

v2.473 - 2021/04/18
-------------------

**SMONSTER**

• Added new command to Set All Smonster Keymaps To True (Set to Default Keymaps)

**GAME CONTENT**

• New command added via Right Click Item Context Menu:
  • SoloInstanceInPlace
  • Isolate Item and Instances

**MIFABOMA**

• Bugfix on Radial Sweep Local that wasn't working if the Reference System was already defined.

**COLOR BAR**

• New Locator on Meshes via Locator To Shape Vertical Popover Menu.

**BAKE**

• Groups Reordering Top/Down to Set Bake Pairs grouping feature.
• New command added via Right Click Item Context Menu:
  • Create Pairs from Highpoly Mesh

**CAD**

• 3 New Mouse Over Commands
  • Star Triple Flat
  • Rebuild Radial Flat
  • Rebuild Radial Tube



.. _2460:

v2.460 - 2021/04/11
-------------------

**SMONSTER**

• Icons Added for CLEANUP
• BugFix on Documentation Links (CLEANUP - VENOM) and Menus (changed as separate forms)

**BATCH**

• BugFix on LXO to DXF. 
• Corrected a bug on the Export Game Ready for Bakes command

**BAKE & MARMOSET LIVELINK**

• New Function to put automatically HighPoly and LowPoly Meshes layers in a dedicated Group (Groups Tab) via Set Bake Pairs Command.
• New Function to Detect if a Cage map is set or Not. If not, it create one for you, but show you that that mesh have missing data in it.

**BAKE**

• Changed the Training Scene Files
• Update on Forms Menu

**CAD**

• added the Rebuild Polystrip Commands and Menus.
  • 2 Methods are available. (Select a Polygon Selection and 2 partial Edge loop to define the shape.)
    • Regular rebuild
    • Normalized Width



.. _1424:

v1.424 - 2021/03/10
--------------------

**SMONSTER**

• Icons Added for BAKE and BATCH

**BAKE**

• Corrected an issue that was affecting that Kit as well as MARMOSET LL on Modo 13.X Releases.
• Corrected a bug on the Export Game Ready for Bakes command

**MIFABOMA**

• Bugfix on Vertical Menu (missing Commands and UserPref )

**PIXAFLUX LIVELINK**

• Updated Icons

**ALL LIVELINKS Kits**

• Added a Direct Link to their respective Website under the Tail Menus



.. _1416:

v1.416 - 2021/02/24
-------------------

**SMONSTER**

• Compatibility upgrade to 15.X release (this include the current Public Beta).
• Full Support of the kit in both Python 2X and Python 3.X mode.
• Added CmdList.txt to get the full list of commands available.
• Added SmonsterKitUpdateLog.docx and UpdateLog.txt to get the full log of updates.

**COLOR BAR**

• Added a new Bar for setting Locator Shapes. Available via "Shift - f8".

**MARMOSET TOOLBAG LIVELINK**

• Now option to Create and Set automatically a Mikk Tangent Space map at export.

**PIXAFLUX LIVELINK**

• Bugfix on NormalMap effect mode. Now it switch directly to Normalmap after bake is done.
• Bugfix on Popover Tail Menu.
• Bugfix on still present Keymap.cfg even if keymapCommander was introduced.



.. _1398:

v1.398 - 2021/02/14
-------------------

**GAME CONTENT**

• Bugfix on (Ctrl + numpad "6") Keymap and "Cycle Through MatCaps" Command.
  • Ctrl + numapd "6" 	-- > Cycle to Next Matcap
  • Ctrl + Alt + numapd "6" -- > Cycle to Previous Matcap
• Added Hughsk Matcaps and Nidorx Matcap Library Links from Github.
  • https://github.com/hughsk/matcap
  • https://github.com/nidorx/matcaps



.. _1395:

v1.395 - 2021/02/10
-------------------

**SMONSTER**

• Menus and Keymap Commander Bugfixes



.. _1387:

v1.387 - 2021/02/06
-------------------

**SMONSTER**

• New checkup procedure at Modo launch to see if you've updated the Kit recently.
• All new Input Remapping Menu to manage your Hotkeys for all Smonster's kits via the SMONSTER Top Menu
• Uncheck the checkbox in prompt menu to be sure the kit will not erase your remapping if desired.
• Set all the Smonster Default Hotkey in one click.

**MARMOSET TOOLBAG LIVELINK**

• Bugfix and Support now for HighPoly created via MehsFusion and/or Meshops setup. Smonster now Freeze the result for export, but preserve the scene state.
• Added function to add a Position/Rotation Constraint to HighPoly mesh item (driven by LowpPoly mesh item) for ease update.

**GAME CONTENT**

• New AttachScriptToPreset features to let you create optimized Mesh Presets library.
• New Render Thumbnail for Mesh Preset with a Built-in scene with Dynamic Scaled Grid.



.. _1345:

v1.345 - 2021/01/18
-------------------

**MARMOSET TOOLBAG LIVELINK**

• Automatic Bake at data load.
• Automatically close Marmoset after Bake is finished
• Automatically save a Marmoset Scene file as backup of the current Data processed
• Bugfix on Bake File Output that was asking to user to create the file.
• Added Item Index Style Prefs to be sure the Marmoset and Bake Renaming will work by using Underscore system.
• Now 4 Output File format type are supported ( PSD , JPG , TGA, PNG )
• Now Possibility to define your own Baked File Name Prefix for the bakes.
• Baked File Name Prefix Presets:
• 3 Presets available and more to come. (SMOLUCK / Substance Painter Default / Vladimir Leleiva)
• Now Ability to define your Normal Map workflow. OpenGL to DirectX or OpenGL to OpenGL

**UV**

• Added a new command: Unwrap_By_SharpEdge to quickly unwrap buildings an other man made props.

**GAME CONTENT**

• Get back the Senemodo Supertaut piemenu on Ctrl+Alt + L if you have this kit.

**CLEANUP**

• Added cleanup function smo.CLEANUP.ConvertItemIndexStyleSceneWise and updated smo.CLEANUP.FullAutoCleanup to support it.



.. _1314:

v1.314 - 2020/12/26
-------------------

**MARMOSET TOOLBAG LIVELINK**

• Now all necessarry Modo data and settings are sent to Marmoset.
• New Folder organization. Subfolder in temp folder using Scene name as well as Subfolder in Scene path if chosen.
• Added support for Material ID / Albedo from materials / UV Island ID.
• Resolution of bakes can be set in Modo now.
• Bugfix on Smo.Cleanup.DeleteEmptyMeshes
• Added new video link to Documentation for SMO BAKE and SMO MARMOSET LL



.. _1300:

v1.300 - 2020/12/16
-------------------

**BATCH**

• Command to RenameMeshesBySceneName
• Command to ConvertSceneToXFiles
• Batch Process to convert Data from various file format (DXF, FBX, LXO, OBJ, SVG)
• 20 Customizable command lines for more flexibility

**BAKE**

• Command for creating Low and High Poly mesh pairs.
• Command for creating a Cage Export ready group of meshes.
• Command for creating Freezing the Highpoly Subdiv or Catmull-Clark Polys.
• Presets for Edge Padding to quick access before Bake.

**MARMOSET TOOLBAG LIVELINK**

• Rebuild the command from scratch to make it more flexible and robust.
• Automatic export of Low / High / Cage meshes to setup bakes in Toolbag and get back the textures in Modo to check the result.
• Automatic Freeze of the Highpoly Subdiv or Catmull-Clark Polys on export.
• Centralization of all Smonster Commands in order to let them be used in any sub-category Kits (whenever they are loaded or not).
• Renaming of few commands to get more consistency across all kits.
• Externalized the Copy/Paste preferences out of the Kit, in order to let users define their own workflow settings.
• Corrected Color Bar kit. Now it doesn't show up a runtime error in event log when used.
• BugFix on tail menu icons, organization and labels



.. _1196:

v1.196 - 2020/09/22
-------------------

**VENOM**

• Bugfix that was affecting VeNom result when the Item was having Rotations different than Zero or part of a Hierarchy.

**GAME CONTENT**

• Extracted the UV Map name setting out of the Kit (now it will use your own preferences).
• Extracted the Tool Handle Advanced Mode setting out of the Kit (now it will use your own preferences).



.. _1190:

v1.190 - 2020/09/12
-------------------

**VENOM**

• (use it in 14.1 for full support) (14.0 and Older Modo release will not support "Undo" and will cause modo to crash)

**MARMOSET TOOLBAG LIVELINK**

• Added the SMONSTER Top Menu to get quick access to some menus without viewing the Modo Tail Kit bar.
• (with Documentation and Training Scenes for Kit learning and debug test.)
• Update on Icons.
• Bugfix on 14.1 that was asking for confirmation on few Scripts where a delete procedure was included.
• Update UV Seam Cut Map toggle added to Preferences.
• Support for multiple UV Maps on every Unwrap tools (Planar / Cylindrical / Unwrap)
• Bug fix in UV Tools.



.. _1160:

v1.160 - 2020/07/25
-------------------

**PIXAFLUX LIVELINK**

• Added this new kit.

**SMONSTER**

• Various bugfix and improvement on UV Kit as well as CLEANUP, GAME CONTENT (GC) and MIFABOMA



.. _1138:

v1.138 - 2020/06/27
-------------------

**RIZOMUV LIVELINK**

• RizomUV LiveLink Kit updated to 2.1: Fixed an issue where RizomUVLL was exporting the mesh triangulated if you was exporting Triangulated FBX previously using the RizomUV LL commands in the same scene.



.. _1135:

v1.135 - 2020/06/22
-------------------

**QUICK TAG**

• Added Bugfix for SetColorID by Selection Set.



.. _1135:

v1.130 - 2020/06/21
-------------------

**CLEANUP**

• BugFix and Added User prefs string to search and replace UVMap Name from Source (string) to Target (string).

**GAME CONTENT**

• Added: Rotate Center to Selection.
• Added: Move and Rotate center to Mesh open boundary center.
• Added: Replace Target by Instance.



.. _1118:

v1.118 - 2020/06/17
-------------------

**MIFABOMA**

• Bugfix on Radial tools on Meshitem that where not part of a hierarchy (at the scene root level).



.. _1116:

v1.116 - 2020/06/15
-------------------

**MIFABOMA**

• Bugfix on Radial tools in Item Mode.
• Added Radial Array by User Count.
• Added Radial Sweep by User Count.

**GAME CONTENT**

• Updated Pie Menus.

**MESHOPS**

• Isolated currently in Dev Meshops to be released in SMO MESHOPS Kit in separate folder "TO_CHECK".
• Released new meshops:
  • SMO_ARROW
  • SMO_STEPS_RING
  • SMO_STEPS_SIMPLE
  • SMO_STEPS_STAIRS
  • SMO_TUBULAR_ZIGZAG_v1



.. _1094:

v1.094 - 2020/05/30
-------------------

**MIFABOMA**

• Bugfix on Mirror Pie Menu icons. New icon for "Relative to Parent"



.. _1094:

v1.091 - 2020/05/28
-------------------

**UV**

• Bugfix at UV Smart Projection Planar SPP command in first Execution after installing the script.

**MIFABOMA**

• Bugfix on Mirror pie menu using the new set of icons for Local/World/Relative to Parent.



.. _1088:

v1.088 - 2020/05/26
-------------------

**MIFABOMA**

• Radial Array and Mirror Bugfix (to use the User Values (Clone type and Clone Hierarchy))



.. _1086:

v1.086 - 2020/05/25
-------------------

**SMONSTER**

• Major BugFix on Icons (Location Broken on Mac and PC). (Thanks to Jörg)
        
 **GAME CONTENT**
 
• Bugfix on Input Remapping that was setting the keymap navigation to Maya only. (Now you're free to use what you want.)
        
**MIFABOMA**

• Added User Value in preferences for Radial and Mirror commands via SMO MIFABOMA Options (Preferences panel)
        
**QUICK TAG**

• Added the Quick Tag - Set ColorID command to polygons



.. _1078:

v1.078 - 2020/05/22
-------------------

**SMONSTER**

• Moved the AI tools Teaser & Unbevel videos out of the LPK installation.

**MIFABOMA**

• Radial Array and Radial Sweep Command Added (Features update and BugFix) --> Mode Local / World / Relative to Parent
        
**RIZOMUV LIVELINK**

• Set path command to directly change the Rizom Release you want to work with. No need to to edit the Python script, and now you are able to choose the release to work with , without rebooting Modo.
• Kit Preferences Menu available in Modo Preferences Window.
        


.. _1064:

v1.064 - 2020/05/17
-------------------

**SMONSTER**

• Consolidated and separate SMO Kits Preferences Forms.
• Added MASTER Kit to hold the Smonster general preferences and Documentation.

**MIFABOMA**

• Added RADIAL ARRAY
• Bugfix on few icons destination
        
**CLEANUP**

• Changed all CLEANUP Commands to use User defined Preferences.
• Added the FullAuto Cleanup Command to batch Cleanup based on User Prefs.



.. _1053:

v1.053 - 2020/05/13
-------------------

**UV**

• Fixed wrong folder address for icons referencing.
• Added the Option in UV Kit to Pack in the Main Zero / One Area via User Prefs.
        
**RIZOMUV LIVELINK**

• RizomUV Offline bridge updated.
• Bugfix on RizomUV LL to use only FBX 2013 for all Import / Exports from whatever Modo release to fix incompatibility.

**MESHOPS**

• Started to update MeshopsAssAliases.
• Fixed Issue and separate Meshops Assembly Aliases in 2 folders v1 and v2.



.. _1046:

v1.046 - 2020/05/10
-------------------

**UV**

• Updated SMO UV Kit for new PieMenu and customizable workflow via Preferences.
• Various bugfix.



.. _1032:

v1.032 - 2020/05/04
-------------------

• Improvement of Code in many Scripts that were using selection commands. (Simplified select by type commands).

**CAD**

• BugFixes. (Fixed issue with LazySelect that was pointing to the wrong Kit scripts folder).
        
**UV**

• UV Smart Projection Tools compiled in a new Pie Menu for SP Planar / Cylindrical / Unwrap. (Added Q key in viewport).
• Updated Icons.



.. _1026:

v1.026 - 2020/04/30
-------------------

**UV**

• Fixed some issue on tool-tips and forms.

**MIFABOMA**

• Added the new Slice and Flip On Axis tools.   