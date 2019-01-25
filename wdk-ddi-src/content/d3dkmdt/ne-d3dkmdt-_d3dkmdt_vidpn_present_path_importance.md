---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
title: "_D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE" (d3dkmdt.h)
description: The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path.
old-location: display\d3dkmdt_vidpn_present_path_importance.htm
tech.root: display
ms.assetid: a48eda3c-84cb-4413-a325-79c330be3f18
ms.date: 05/10/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration [Display Devices], D3DKMDT_VPPI_DENARY, D3DKMDT_VPPI_NONARY, D3DKMDT_VPPI_OCTONARY, D3DKMDT_VPPI_PRIMARY, D3DKMDT_VPPI_QUATERNARY, D3DKMDT_VPPI_QUINARY, D3DKMDT_VPPI_SECONDARY, D3DKMDT_VPPI_SENARY, D3DKMDT_VPPI_SEPTENARY, D3DKMDT_VPPI_TERTIARY, D3DKMDT_VPPI_UNINITIALIZED, DmEnums_711fdb2d-86cd-4ac4-9529-818b3953dff5.xml, _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE, d3dkmdt/D3DKMDT_VPPI_DENARY, d3dkmdt/D3DKMDT_VPPI_NONARY, d3dkmdt/D3DKMDT_VPPI_OCTONARY, d3dkmdt/D3DKMDT_VPPI_PRIMARY, d3dkmdt/D3DKMDT_VPPI_QUATERNARY, d3dkmdt/D3DKMDT_VPPI_QUINARY, d3dkmdt/D3DKMDT_VPPI_SECONDARY, d3dkmdt/D3DKMDT_VPPI_SENARY, d3dkmdt/D3DKMDT_VPPI_SEPTENARY, d3dkmdt/D3DKMDT_VPPI_TERTIARY, d3dkmdt/D3DKMDT_VPPI_UNINITIALIZED, display.d3dkmdt_vidpn_present_path_importance
ms.topic: enum
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE
---

# _D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration


## -description


The D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE enumeration indicates the importance of a video present path.


## -enum-fields




### -field D3DKMDT_VPPI_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE has not yet been assigned a meaningful value.


### -field D3DKMDT_VPPI_PRIMARY

Indicates importance level 1.


### -field D3DKMDT_VPPI_SECONDARY

Indicates importance level 2.


### -field D3DKMDT_VPPI_TERTIARY

Indicates importance level 3.


### -field D3DKMDT_VPPI_QUATERNARY

Indicates importance level 4.


### -field D3DKMDT_VPPI_QUINARY

Indicates importance level 5.


### -field D3DKMDT_VPPI_SENARY

Indicates importance level 6.


### -field D3DKMDT_VPPI_SEPTENARY

Indicates importance level 7.


### -field D3DKMDT_VPPI_OCTONARY

Indicates importance level 8.


### -field D3DKMDT_VPPI_NONARY

Indicates importance level 9.


### -field D3DKMDT_VPPI_DENARY

Indicates importance level 10.


## -remarks



As the numeric value of a D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE value increases, the importance decreases. For example, level 3 is less important than level 2.

A variable of type D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE can have any integer value in the range 0 through 255, but only the values 0 through 10 have names.

It is useful to rank the video present paths in a video present network (VidPN) according to importance. For example, a path that represents the primary view can be assigned a higher importance than other paths so that it gets the best source and target mode sets.

The <b>ImportanceOrdinal</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE value. Path importance ordinal numbers are unique within a given VidPN topology. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff546647">D3DKMDT_VIDPN_PRESENT_PATH</a>
 

 

