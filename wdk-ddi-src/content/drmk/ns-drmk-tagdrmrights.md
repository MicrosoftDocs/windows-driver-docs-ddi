---
UID: NS:drmk.tagDRMRIGHTS
title: tagDRMRIGHTS
author: windows-driver-content
description: The DRMRIGHTS structure specifies the DRM content rights assigned to a KS audio pin or to a port-class driver's stream object.
old-location: audio\drmrights.htm
old-project: audio
ms.assetid: 890f996c-9216-4148-b198-538963101c2a
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: tagDRMRIGHTS, DRMRIGHTS, *PDRMRIGHTS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: drmk.h
req.include-header: Drmk.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DRMRIGHTS
req.alt-loc: drmk.h
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
req.typenames: DRMRIGHTS, *PDRMRIGHTS
---

# tagDRMRIGHTS structure



## -description
The <b>DRMRIGHTS</b> structure specifies the DRM content rights 
   assigned to a KS audio pin or to a port-class driver's stream object.



## -syntax

````
typedef struct tagDRMRIGHTS {
  BOOL  CopyProtect;
  ULONG Reserved;
  BOOL  DigitalOutputDisable;
} DRMRIGHTS, *PDRMRIGHTS;
````


## -struct-fields

### -field CopyProtect

Specifies one of the following copy-protection values:
	   




### -field TRUE

Enables copy protection. An audio application must not do the following:
		   

<ul>
<li>
Store the content in any form in any nonvolatile storage.

</li>
<li>
Pass the content by reference or by value to any other component within the host system that is not 
			   authenticated by the DRM system.

</li>
</ul>

### -field FALSE

Disables copy protection. Content can be copied without restrictions.

</dd>
</dl>
For more information about <b>CopyProtect</b>, see the Remarks section.


### -field Reserved

Reserved for future use. Initialize to zero.


### -field DigitalOutputDisable

Specifies one of the following digital output protection values:




### -field TRUE

Disable digital outputs. A software component must not transfer the content out of the host system through any type of digital interface. Note that digital output protection does not affect USB devices because the host system includes USB devices.


### -field FALSE

Enables digital outputs. Content can be transferred from the host system to an external component without restrictions.

</dd>
</dl>
For more information about <b>DigitalOutputDisable</b>, see the Remarks section.


## -remarks
The Windows Certification Program places specific requirements on the way an audio driver handles the <b>CopyProtect</b> and <b>DigitalOutputDisable</b> values. These requirements are applicable when the <b>CopyProtect</b> and <b>DigitalOutputDisable</b> values are applied to an audio stream and to the output from which the audio stream is accessed. New requirements for Windows 7 include the correct way to program the serial copy management system (SCMS) for S/PDIF endpoints, and high-bandwidth digital content protection (HDCP) for HDMI endpoints.

The following table summarizes the content protection state that the driver must establish for different values of <b>CopyProtect</b> and <b>DigitalOutputDisable</b>.

<b>DRMRIGHTS Boolean members</b>

<b>Resulting content protection</b>

<b>DigitalOutputDisable</b>

<b>CopyProtect</b>

<b>
        HDMI and Display port</b>

<b>S/PDIF</b>

False

Enabled with no HDCP

Enabled with no SCMS

True

Enabled with HDCP

Enabled with SCMS

Don't care

Disabled

When an audio driver applies SCMS copy protection to a S/PDIF endpoint, the audio driver uses a combination of the L, Cp, and Category Code bits to select an SCMS state of "Copy Never." For more information about copy protection for digital content, see <a href="http://go.microsoft.com/fwlink/p/?linkid=158256">IEC 60958</a> on the IEC website.

If the driver supports DRMRIGHTS and also implements a proprietary copy protection mechanism, the driver must aggregate the result of the proprietary implementation with the values of <b>CopyProtect</b> and <b>DigitalOutputDisable</b> to determine the final copy protection state. The final copy protection state must be the most restrictive of all outstanding copy protection requests. 

The <b>DEFINE_DRMRIGHTS_DEFAULT</b> macro defines a constant <b>DRMRIGHTS</b> structure that specifies default DRM content rights.

Parameters


## -see-also
<dl>
<dt>
<a href="..\drmk\nf-drmk-drmcreatecontentmixed.md">DrmCreateContentMixed</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmdestroycontent.md">DrmDestroyContent</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttofileobject.md">DrmForwardContentToFileObject</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmforwardcontenttointerface.md">DrmForwardContentToInterface</a>
</dt>
<dt>
<a href="..\drmk\nf-drmk-drmgetcontentrights.md">DrmGetContentRights</a>
</dt>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=158256">IEC 60958</a></dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20DRMRIGHTS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

