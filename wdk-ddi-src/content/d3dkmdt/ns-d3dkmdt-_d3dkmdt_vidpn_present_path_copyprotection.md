---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
title: "_D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_copyprotection.htm
old-project: display
ms.assetid: 661e70c6-d99e-4c5a-ad88-3dd854747de4
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, display.d3dkmdt_vidpn_present_path_copyprotection, _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION, DmStructs_512b61d6-627d-4423-93ba-0f28ac340e51.xml, D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure [Display Devices], D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
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
-	D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION
---

# _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure


## -description


The D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure contains information about the copy protection that is supported (as well as the copy protection that is currently active) on a particular VidPN present path.


## -syntax


````
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION {
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE    CopyProtectionType;
  UINT                                              APSTriggerBits;
  BYTE                                              OEMCopyProtection[D3DKMDT_MACROVISION_OEMCOPYPROTECTION_SIZE];
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT CopyProtectionSupport;
} D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION;
````


## -struct-fields




### -field CopyProtectionType

A value from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection_type.md">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_TYPE</a> enumeration that indicates the type of copy protection that is active on the path.


### -field APSTriggerBits

A value that describes copy protection for an OEM device. A value of 0 indicates no copy protection, and values of 1, 2, and 3 indicate low, medium, and high levels of copy protection, respectively. Values greater than 3 are not allowed.


### -field OEMCopyProtection

Reserved for future use.


### -field CopyProtectionSupport

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection_support.md">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION_SUPPORT</a> structure that indicates the types of copy protection that are supported by the path.


## -remarks


The <b>CopyProtection</b> member of the  <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION structure.


