---
UID: NS:d3dumddi.D3DDDIARG_CHECKPRESENTDURATIONSUPPORT
title: D3DDDIARG_CHECKPRESENTDURATIONSUPPORT (d3dumddi.h)
description: Used in a call to the CheckPresentDurationSupport function to check details on hardware device support for seamlessly switching to a new monitor refresh rate.
old-location: display\d3dddiarg_checkpresentdurationsupport.htm
tech.root: display
ms.assetid: D72D6C06-DD6A-4051-9AD0-FD1E240C164A
ms.date: 05/10/2018
keywords: ["D3DDDIARG_CHECKPRESENTDURATIONSUPPORT structure"]
ms.keywords: D3DDDIARG_CHECKPRESENTDURATIONSUPPORT, D3DDDIARG_CHECKPRESENTDURATIONSUPPORT structure [Display Devices], d3dumddi/D3DDDIARG_CHECKPRESENTDURATIONSUPPORT, display.d3dddiarg_checkpresentdurationsupport
f1_keywords:
 - "d3dumddi/D3DDDIARG_CHECKPRESENTDURATIONSUPPORT"
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- D3dumddi.h
api_name:
- D3DDDIARG_CHECKPRESENTDURATIONSUPPORT
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_CHECKPRESENTDURATIONSUPPORT
---

# D3DDDIARG_CHECKPRESENTDURATIONSUPPORT structure


## -description


Used in a call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_checkpresentdurationsupport">CheckPresentDurationSupport</a> function to check details on hardware device support for seamlessly switching to a new monitor refresh rate.


## -struct-fields




### -field VidPnSourceId

[in] The zero-based video present network (VidPN) source identification number of the input for which the hardware support is queried.


### -field DesiredPresentDuration

[in] The desired duration of a single present operation, in units of 100 nanoseconds.


### -field ClosestSmallerDuration

[out] The smallest supported desired duration of a single present operation on the given VidPN source, in units of 100 nanoseconds. The value must be ≤ <b>DesiredPresentDuration</b>.

See Remarks for more limitations on this value.


### -field ClosestLargerDuration

[out] The largest supported desired duration of a single present operation on the given VidPN source, in units of 100 nanoseconds. The value must be ≥ <b>DesiredPresentDuration</b>.

See Remarks for more limitations on this value.


## -remarks



Either  <b>ClosestSmallerDuration</b> or <b>ClosestLargerDuration</b> can be zero. However, if both  are zero, the device cannot seamlessly switch to a new refresh rate.

If both <b>ClosestSmallerDuration</b> and <b>ClosestLargerDuration</b> have the same value as <b>DesiredPresentDuration</b>, the device can precisely match <b>DesiredPresentDuration</b>.

The difference between <b>DesiredPresentDuration</b> and <b>ClosestSmallerDuration</b> (or <b>ClosestLargerDuration</b>) represents the driver’s knowledge of the device capabilities, but there will be additional error during execution. The final accuracy of the device when using per-present durations should typically be the same as the accuracy using  existing presentation modes.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_checkpresentdurationsupport">CheckPresentDurationSupport</a>
 

 

