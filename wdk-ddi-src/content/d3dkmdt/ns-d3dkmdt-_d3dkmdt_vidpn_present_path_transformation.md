---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
title: "_D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure contains information about the transformations (for example, rotation, scaling, centering) that are pinned and the transformations that are supported for a path in a video present network (VIDPN).
old-location: display\d3dkmdt_vidpn_present_path_transformation.htm
old-project: display
ms.assetid: 7b2370c8-ea8a-4719-b88a-2401dbafb64c
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION, _D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION, DmStructs_3c1dd0fd-471f-48e0-9df5-003f98237ac2.xml, D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure [Display Devices], display.d3dkmdt_vidpn_present_path_transformation, D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmdt.h
apiname:
-	D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION
---

# _D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure


## -description


The <b>D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</b> structure contains information about the transformations (for example, rotation, scaling, centering) that are pinned and the transformations that are supported for a path in a video present network (VIDPN).


## -syntax


````
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION {
  D3DKMDT_VIDPN_PRESENT_PATH_SCALING          Scaling;
  D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT  ScalingSupport;
  D3DKMDT_VIDPN_PRESENT_PATH_ROTATION         Rotation;
  D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT RotationSupport;
} D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION;
````


## -struct-fields




### -field Scaling

A value from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling.md">D3DKMDT_VIDPN_PRESENT_PATH_SCALING</a> enumeration that indicates the type of scaling (or centering) that is currently set for the path. If this member is equal to <b>D3DKMDT_VPPS_IDENTITY</b>, <b>D3DKMDT_VPPS_CENTERED</b>, <b>D3DKMDT_VPPS_STRETCHED</b>, <b>D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX</b>, or <b>D3DKMDT_VPPS_CUSTOM</b>, then the indicated scaling type is considered pinned for the path. If this member is equal to any other value, then no scaling type is pinned for the path.

For more information on how to use this member, see the Remarks section.


### -field ScalingSupport

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling_support.md">D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT</a> structure that holds a set of flags that indicate the types of scaling that are supported by the path.


### -field Rotation

A value from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a> enumeration that indicates the type of rotation that is currently set for the path. If this member is equal to <b>D3DKMDT_VPPR_IDENTITY</b>, <b>D3DKMDT_VPPR_ROTATE90</b>, <b>D3DKMDT_VPPR_ROTATE180</b> or <b>D3DKMDT_VPPR_ROTATE270</b>, then the indicated rotation type is considered pinned for the path. If this member is equal to any other value, then no rotation type is pinned for the path.


### -field RotationSupport

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation_support.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT</a> structure that holds a set of flags that indicate the types of rotation that are supported by the path.


## -remarks



The <b>ContentTransformation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a  <b>D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</b> structure.

If <b>D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX</b> or <b>D3DKMDT_VPPS_CUSTOM</b> values are specified in the <b>Scaling</b> member but the path is on a display miniport driver that does not support these values (which are available beginning with Windows 7), the driver's calls to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a> should return <b>STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED</b>, and the operating system will apply the system default scaling. If a driver cannot support the requested scaling value on the specified path, its calls to <b>DxgkDdiCommitVidPn</b> should return <b>STATUS_GRAPHICS_VIDPN_MODALITY_NOT_SUPPORTED</b>.

<div class="alert"><b>Note</b>    A display miniport driver that supports the <b>D3DKMDT_VPPS_ASPECTRATIOCENTEREDMAX</b> or <b>D3DKMDT_VPPS_CUSTOM</b> values should never set a value of <b>D3DKMDT_VPPS_NOTSPECIFIED</b>.</div>
<div> </div>



## -see-also

<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling.md">D3DKMDT_VIDPN_PRESENT_PATH_SCALING</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_scaling_support.md">D3DKMDT_VIDPN_PRESENT_PATH_SCALING_SUPPORT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_commitvidpn.md">DxgkDdiCommitVidPn</a>



<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation_support.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION_SUPPORT</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_enumvidpncofuncmodality.md">DxgkDdiEnumVidPnCofuncModality</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_rotation.md">D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION structure%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

