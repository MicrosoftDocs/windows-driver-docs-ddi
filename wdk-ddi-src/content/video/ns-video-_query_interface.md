---
UID: NS:video._QUERY_INTERFACE
title: "_QUERY_INTERFACE"
author: windows-driver-content
description: The QUERY_INTERFACE structure describes the interface being requested.
old-location: display\query_interface.htm
old-project: display
ms.assetid: 0d813870-10bd-4b41-9f36-1cb45c462697
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: "_QUERY_INTERFACE, video/QUERY_INTERFACE, QUERY_INTERFACE structure [Display Devices], display.query_interface, Video_Structs_facaef96-c0d9-4695-8541-65e5e430f182.xml, PQUERY_INTERFACE, video/PQUERY_INTERFACE, QUERY_INTERFACE, *PQUERY_INTERFACE, PQUERY_INTERFACE structure pointer [Display Devices]"
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
req.irql: See Remarks section.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	video.h
apiname:
-	QUERY_INTERFACE
product: Windows
targetos: Windows
req.typenames: "*PQUERY_INTERFACE, QUERY_INTERFACE"
req.product: Windows 10 or later.
---

# _QUERY_INTERFACE structure


## -description


The QUERY_INTERFACE structure describes the interface being requested.


## -syntax


````
typedef struct _QUERY_INTERFACE {
  const GUID *InterfaceType;
  USHORT     Size;
  USHORT     Version;
  PINTERFACE Interface;
  PVOID      InterfaceSpecificData;
} QUERY_INTERFACE, *PQUERY_INTERFACE;
````


## -struct-fields




### -field InterfaceType

Pointer to a GUID that identifies the interface being requested. If the miniport driver does not support the specified <b>InterfaceType</b>, it should fail the call and return immediately.

The parent generates this GUID with <i>uuidgen.exe</i>. See <a href="https://msdn.microsoft.com/library/windows/hardware/ff542998">Defining and Exporting New GUIDs</a> for details.


### -field Size

Specifies the size in bytes of the <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure to which <b>Interface</b> points. The miniport driver must not return an INTERFACE structure larger than <b>Size</b> bytes.


### -field Version

Specifies the version of the interface being requested.

If a parent supports more than one version of an interface, its driver should return the specified version or, if possible, the closest supported version without exceeding the requested version. It is the querying driver's responsibility to examine the returned <b>Version</b> and determine what to do based on that value.


### -field Interface

Pointer to an <a href="..\wdm\ns-wdm-_interface.md">INTERFACE</a> structure in which the miniport driver returns the requested interface information. The querying driver is responsible for allocating this structure before calling <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>.


### -field InterfaceSpecificData

Specifies additional information about the interface being requested. Typically, this member is <b>NULL</b>, and the <b>InterfaceType</b> and <b>Version</b> members are sufficient for the parent to identify the interface being requested.


### -field DeviceUid

 




## -remarks



The <i>QueryInterface</i> parameter of the video miniport driver's <a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a> function is a pointer to a QUERY_INTERFACE structure. 




## -see-also

<a href="..\video\nc-video-pvideo_hw_query_interface.md">HwVidQueryInterface</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20QUERY_INTERFACE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

