---
UID: NS:video._QUERY_INTERFACE
title: "_QUERY_INTERFACE"
author: windows-driver-content
description: The QUERY_INTERFACE structure describes the interface being requested.
old-location: display\query_interface.htm
old-project: display
ms.assetid: 0d813870-10bd-4b41-9f36-1cb45c462697
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: "*PQUERY_INTERFACE, PQUERY_INTERFACE, PQUERY_INTERFACE structure pointer [Display Devices], QUERY_INTERFACE, QUERY_INTERFACE structure [Display Devices], Video_Structs_facaef96-c0d9-4695-8541-65e5e430f182.xml, _QUERY_INTERFACE, display.query_interface, video/PQUERY_INTERFACE, video/QUERY_INTERFACE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: video.h
req.include-header: Video.h
req.target-type: Windows
req.target-min-winverclnt: 
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
-	video.h
api_name:
-	QUERY_INTERFACE
product: Windows
targetos: Windows
req.typenames: QUERY_INTERFACE, *PQUERY_INTERFACE
---

# _QUERY_INTERFACE structure


## -description


The QUERY_INTERFACE structure describes the interface being requested.


## -struct-fields




### -field InterfaceType

Pointer to a GUID that identifies the interface being requested. If the miniport driver does not support the specified <b>InterfaceType</b>, it should fail the call and return immediately.

The parent generates this GUID with <i>uuidgen.exe</i>. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff542998">Defining and Exporting New GUIDs</a> for details.


### -field Size

Specifies the size in bytes of the <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure to which <b>Interface</b> points. The miniport driver must not return an INTERFACE structure larger than <b>Size</b> bytes.


### -field Version

Specifies the version of the interface being requested.

If a parent supports more than one version of an interface, its driver should return the specified version or, if possible, the closest supported version without exceeding the requested version. It is the querying driver's responsibility to examine the returned <b>Version</b> and determine what to do based on that value.


### -field Interface

Pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/dn895657">INTERFACE</a> structure in which the miniport driver returns the requested interface information. The querying driver is responsible for allocating this structure before calling <a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a>.


### -field InterfaceSpecificData

Specifies additional information about the interface being requested. Typically, this member is <b>NULL</b>, and the <b>InterfaceType</b> and <b>Version</b> members are sufficient for the parent to identify the interface being requested.


### -field DeviceUid

 




## -remarks



The <i>QueryInterface</i> parameter of the video miniport driver's <a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a> function is a pointer to a QUERY_INTERFACE structure. 




## -see-also




<a href="https://msdn.microsoft.com/f16a7fa3-3471-4ccb-b1b4-982d33f930d3">HwVidQueryInterface</a>
 

 

