---
UID: NS:ksmedia.KSPROPERTY_CAMERACONTROL_S_EX
title: KSPROPERTY_CAMERACONTROL_S_EX
author: windows-driver-content
description: Specifies a camera control operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization.
old-location: stream\ksproperty_cameracontrol_s_ex.htm
old-project: stream
ms.assetid: fa015adf-93b6-472f-8a78-a627a59c032e
ms.author: windowsdriverdev
ms.date: 4/23/2018
ms.keywords: "*PKSPROPERTY_CAMERACONTROL_S_EX, KSPROPERTY_CAMERACONTROL_FLAGS_ASYNCHRONOUS, KSPROPERTY_CAMERACONTROL_FLAGS_AUTO, KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL, KSPROPERTY_CAMERACONTROL_S_EX, KSPROPERTY_CAMERACONTROL_S_EX structure [Streaming Media Devices], PKSPROPERTY_CAMERACONTROL_S_EX, PKSPROPERTY_CAMERACONTROL_S_EX structure pointer [Streaming Media Devices], ksmedia/KSPROPERTY_CAMERACONTROL_S_EX, ksmedia/PKSPROPERTY_CAMERACONTROL_S_EX, stream.ksproperty_cameracontrol_s_ex"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	Ksmedia.h
api_name:
-	KSPROPERTY_CAMERACONTROL_S_EX
product: Windows
targetos: Windows
req.typenames: KSPROPERTY_CAMERACONTROL_S_EX, *PKSPROPERTY_CAMERACONTROL_S_EX
---

# KSPROPERTY_CAMERACONTROL_S_EX structure


## -description


Specifies a camera control operation, including setting the flash, the image pin control properties, the region of interest in the image, or video stabilization. This structure describes filter-based properties in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff567802">PROPSETID_VIDCAP_CAMERACONTROL</a> property set.

Supported starting with Windows 8.


## -struct-fields




### -field Property

Specifies an initialized <a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a> structure that describes the property set, property ID, and request type.


### -field Value

Specifies the value of the property. This member is read/write.


### -field Flags

Indicates, for Get requests, the current setting for the specified property from the values listed below. Indicates, for Set requests, the desired setting for the specified property from the values listed below. This member can be a bitwise <b>OR</b> of the following values that are defined in Ksmedia.h:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLAGS_AUTO"></a><a id="ksproperty_cameracontrol_flags_auto"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLAGS_AUTO</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the setting is controlled automatically.
If the driver receives this value, it should set the camera control synchronously to automatic mode and then return.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL"></a><a id="ksproperty_cameracontrol_flags_manual"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL</b></dt>
</dl>
</td>
<td width="60%">
Indicates that the setting is controlled manually. If the driver receives this value, it should set the camera control synchronously to manual mode and then return.

</td>
</tr>
<tr>
<td width="40%"><a id="KSPROPERTY_CAMERACONTROL_FLAGS_ASYNCHRONOUS"></a><a id="ksproperty_cameracontrol_flags_asynchronous"></a><dl>
<dt><b>KSPROPERTY_CAMERACONTROL_FLAGS_ASYNCHRONOUS</b></dt>
</dl>
</td>
<td width="60%">
Indicates whether the driver should perform the camera control operation asynchronously—where the application has issued a command for the driver to set up the camera control settings in advance of taking a picture.

This flag must be set only if either <b>KSPROPERTY_CAMERACONTROL_FLAGS_MANUAL</b> or <b>KSPROPERTY_CAMERACONTROL_FLAGS_AUTO</b> are set.

If this flag value and and the <b>KSPROPERTY_CAMERACONTROL_FLAGS_AUTO</b> flag value are both set, the driver should initiate a worker thread to start one requested control operation and should reject all other requests for the same operation until it has completed the first one. After the operation has successfully completed, the driver should trigger the <a href="https://msdn.microsoft.com/library/windows/hardware/jj714740">KSEVENTSETID_CameraAsyncControl</a> event.

</td>
</tr>
</table>
 


### -field Capabilities

If set, indicates that when the application submits a query, the driver should return the value of the <b>Capabilities</b> member of the appropriate camera control structure from the following list.

<ul>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj151590">KSPROPERTY_CAMERACONTROL_FLASH_S</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj553707">KSPROPERTY_CAMERACONTROL_IMAGE_PIN_CAPABILITY_S</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj151592">KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S</a>
</li>
<li>
<a href="https://msdn.microsoft.com/library/windows/hardware/jj151594">KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S</a>
</li>
</ul>

### -field FocusRect

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a> structure that specifies the rectangular region in which the device should set the focus. This structure is available only to Windows desktop applications.


## -remarks



When a requested camera focus operation is completed or is canceled, the driver should generate an event specified by the <b>KSEVENT_CAMERACONTROL_FOCUS</b> enumeration value.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/jj151587">KSEVENT_CAMERACONTROL</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564262">KSPROPERTY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj151590">KSPROPERTY_CAMERACONTROL_FLASH_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj151592">KSPROPERTY_CAMERACONTROL_REGION_OF_INTEREST_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/jj151594">KSPROPERTY_CAMERACONTROL_VIDEOSTABILIZATION_MODE_S</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569234">RECT</a>
 

 

