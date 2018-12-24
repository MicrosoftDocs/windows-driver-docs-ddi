---
UID: NE:d3dkmddi._DXGK_DISPLAYDETECTCONTROLTYPE
title: "_DXGK_DISPLAYDETECTCONTROLTYPE"
description: Enumeration indicating the type of display detection action.
old-location: display\dxgk_displaydetectcontroltype.htm
ms.assetid: D777342E-439E-4BEF-9DCC-7962B1AF8EAB
ms.date: 05/10/2018
ms.keywords: DXGK_DDCT_DISABLEHPD, DXGK_DDCT_ENABLEHPD, DXGK_DDCT_POLLALL, DXGK_DDCT_POLLONE, DXGK_DDCT_UNINITIALIZED, DXGK_DISPLAYDETECTCONTROLTYPE, DXGK_DISPLAYDETECTCONTROLTYPE enumeration [Display Devices], _DXGK_DISPLAYDETECTCONTROLTYPE, d3dkmddi/DXGK_DDCT_DISABLEHPD, d3dkmddi/DXGK_DDCT_ENABLEHPD, d3dkmddi/DXGK_DDCT_POLLALL, d3dkmddi/DXGK_DDCT_POLLONE, d3dkmddi/DXGK_DDCT_UNINITIALIZED, d3dkmddi/DXGK_DISPLAYDETECTCONTROLTYPE, display.dxgk_displaydetectcontroltype
ms.topic: enum
req.header: d3dkmddi.h
req.include-header: 
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
-	d3dkmddi.h
api_name:
-	DXGK_DISPLAYDETECTCONTROLTYPE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGK_DISPLAYDETECTCONTROLTYPE
---

# _DXGK_DISPLAYDETECTCONTROLTYPE enumeration


## -description


Enumeration indicating the type of display detection action.


## -enum-fields




### -field DXGK_DDCT_UNINITIALIZED

Indicates that a variable of type DXGK_DISPLAYDETECTCONTROLTYPE has not yet been assigned a meaningful value.


### -field DXGK_DDCT_POLLONE

Requests a poll of the target specified in the TargetId field.  The driver should initiate polling the target if the current status is not known.  If the status is not the same as the last reported status for the target, an updated status should be reported using DxgkCbIndicateConnectorChange.


### -field DXGK_DDCT_POLLALL

Request to initiate polls for all targets where the driver does not have current status before completing the call but the driver should not wait for the results of polling before returning.
As status of each target is discovered, if it is not the same as the previously updated status should be reported using DxgkCbIndicateConnectorChange.



### -field DXGK_DDCT_ENABLEHPD

Applies to all targets and requires that the driver enables new notifications and indicates any pending notifications using DxgkCbIndicateConnectorChange before completing the call.  It must also initiate polls for all targets where the driver does not have current status before completing the call but it should not wait for the results of polling before returning. For the POST adapter, it is important that the display which was initialized by firmware be included in the set of displays which is reported before returning from the call made during boot so that the OS is aware of the monitor before it requests the boot functional VidPn.  Since firmware has already detected and initialized the boot display and the driver has been able to query for the frame buffer state, the connection status should naturally be known by the driver and pending notification to the OS.


### -field DXGK_DDCT_DISABLEHPD

Applies to all targets and requires that the driver disables new notifications. It is understood that, this does not prevent an in-flight notification from being reported after the driver has returned.


### -field UINT



