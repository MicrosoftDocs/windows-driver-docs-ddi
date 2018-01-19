---
UID: NC:d3d10umddi.PFND3DWDDM1_3DDI_SETMARKERMODE
title: PFND3DWDDM1_3DDI_SETMARKERMODE
author: windows-driver-content
description: Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.
old-location: display\setmarkermode.htm
old-project: display
ms.assetid: 18B13509-7692-4336-937C-264B31A6FB78
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: SetMarkerMode
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3DWDDM1_3DDI_SETMARKERMODE callback



## -description
Notifies the user-mode display driver that it should support a type of Event Tracing for Windows (ETW) marker event. Must be implemented by Windows Display Driver Model (WDDM) 1.3 and later drivers.



## -prototype

````
PFND3DWDDM1_3DDI_SETMARKERMODE SetMarkerMode;

_Check_return_ HRESULT APIENTRY* SetMarkerMode(
  _In_ D3D10DDI_HDEVICE          hDevice,
  _In_ D3DWDDM1_3DDI_MARKER_TYPE Type,
       UINT                      Flags
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).


### -param Type [in]

A value from the <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_marker_type.md">D3DWDDM1_3DDI_MARKER_TYPE</a> enumeration that indicates the type of marker event  that the driver should support.


### -param Flags 

A <b>UINT</b> value that indicates whether the driver should provide custom info in command buffers. If set to <b>D3DWDDM1_3DDI_SETMARKERMODE_CUSTOMDRIVEREVENTS</b>, the driver should annotate and instrument command buffers with custom event info. Otherwise, the driver should not annotate command buffers.

The annotation can be in the form of a text string in the English-US locale, or in the form of an index value to a location in a string table. For the latter option, the driver must also implement a function that describes the strings that the index values indicate.


## -returns

      Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.


## -remarks
Follow these guidelines when you set up profile-type marker events in your user-mode driver, indicated by the <b>D3DWDDM1_3DDI_MARKER_TYPE_PROFILE</b> type:


## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm1_3ddi_marker_type.md">D3DWDDM1_3DDI_MARKER_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM1_3DDI_SETMARKERMODE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

