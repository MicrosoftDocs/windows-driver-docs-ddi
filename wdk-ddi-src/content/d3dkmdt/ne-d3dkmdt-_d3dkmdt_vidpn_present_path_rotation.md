---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
title: _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration is used to indicate the rotation angle applied to content displayed on a VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_rotation.htm
old-project: display
ms.assetid: 4966ba24-35ed-453a-9483-bd3337e31b83
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION, D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_ROTATION
---

# _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration



## -description
The D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration is used to indicate the rotation angle applied to content displayed on a VidPN present path.



## -syntax

````
typedef enum _D3DKMDT_VIDPN_PRESENT_PATH_ROTATION { 
  D3DKMDT_VPPR_UNINITIALIZED        = 0,
  D3DKMDT_VPPR_IDENTITY             = 1,
  D3DKMDT_VPPR_ROTATE90             = 2,
  D3DKMDT_VPPR_ROTATE180            = 3,
  D3DKMDT_VPPR_ROTATE270            = 4,
#if (DXGKDDI_INTERFACE_VERSION >= DXGKDDI_INTERFACE_VERSION_WDDM1_3_PATH_INDEPENDENT_ROTATION)
  D3DKMDT_VPPR_IDENTITY_OFFSET90    = 5,
  D3DKMDT_VPPR_ROTATE90_OFFSET90    = 6,
  D3DKMDT_VPPR_ROTATE180_OFFSET90   = 7,
  D3DKMDT_VPPR_ROTATE270_OFFSET90   = 8,
  D3DKMDT_VPPR_IDENTITY_OFFSET180   = 9,
  D3DKMDT_VPPR_ROTATE90_OFFSET180   = 10,
  D3DKMDT_VPPR_ROTATE180_OFFSET180  = 11,
  D3DKMDT_VPPR_ROTATE270_OFFSET180  = 12,
  D3DKMDT_VPPR_IDENTITY_OFFSET270   = 13,
  D3DKMDT_VPPR_ROTATE90_OFFSET270   = 14,
  D3DKMDT_VPPR_ROTATE180_OFFSET270  = 15,
  D3DKMDT_VPPR_ROTATE270_OFFSET270  = 16,
#endif 
  D3DKMDT_VPPR_UNPINNED             = 254,
  D3DKMDT_VPPR_NOTSPECIFIED         = 255
} D3DKMDT_VIDPN_PRESENT_PATH_ROTATION;
````


## -enum-fields

### -field D3DKMDT_VPPR_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_ROTATION has not yet been assigned a meaningful value.


### -field D3DKMDT_VPPR_IDENTITY

Indicates that there is no rotation.


### -field D3DKMDT_VPPR_ROTATE90

Indicates that the rotation angle is 90 degrees counter-clockwise.


### -field D3DKMDT_VPPR_ROTATE180

Indicates that the rotation angle is 180 degrees counter-clockwise.


### -field D3DKMDT_VPPR_ROTATE270

Indicates that the rotation angle is 270 degrees counter-clockwise.


### -field D3DKMDT_VPPR_IDENTITY_OFFSET90

Indicates that source content is not modified in any way, and the display miniport driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE90_OFFSET90

Indicates that source content is rotated 90 degrees counter-clockwise, and the driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE180_OFFSET90

Indicates that source content is rotated 180 degrees counter-clockwise, and the driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE270_OFFSET90

Indicates that source content is rotated 270 degrees counter-clockwise, and the driver should rotate this content an extra 90 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_IDENTITY_OFFSET180

Indicates that source content is not modified in any way, and the driver should rotate this content an extra 180 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE90_OFFSET180

Indicates that source content is rotated 90 degrees counter-clockwise, and the driver should rotate this content an extra 180 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE180_OFFSET180

Indicates that source content is rotated 180 degrees counter-clockwise, and the driver should rotate this content an extra 180 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE270_OFFSET180

Indicates that source content is rotated 270 degrees, and the driver should rotate this content an extra 180 degrees. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_IDENTITY_OFFSET270

Indicates that source content is not modified in any way, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE90_OFFSET270

Indicates that source content is rotated 90 degrees counter-clockwise, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE180_OFFSET270

Indicates that source content is rotated 180 degrees counter-clockwise, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_ROTATE270_OFFSET270

Indicates that source content is rotated 270 degrees counter-clockwise, and the driver should rotate this content an extra 270 degrees counter-clockwise. For more info, see Remarks.

Supported starting with Windows 8.1 Update.


### -field D3DKMDT_VPPR_UNPINNED

Indicates that no rotation angle has been pinned for the VidPN present path.


### -field D3DKMDT_VPPR_NOTSPECIFIED

Indicates that no rotation angle (including identity) has been specified.


## -remarks
The <b>Rotation</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> structure is a value from the <b>D3DKMDT_VIDPN_PRESENT_PATH_ROTATION</b> enumeration.

Starting with Windows 8.1 Update, new constant values (<b>D3DKMDT_VPPR_XXX_OFFSETXXX</b>) are available to specify both the default orientation of a display device and an additional angle (offset) that the user has rotated the device.

Here are some examples of how to set the default orientation and offset:


## -see-also
<dl>
<dt>
<a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMDT_VIDPN_PRESENT_PATH_ROTATION enumeration%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

