---
UID: NS:dxva._DXVA_COPPCommand
title: "_DXVA_COPPCommand"
author: windows-driver-content
description: The DXVA_COPPCommand structure describes a command sent to a protected video session that is associated with a COPP DirectX VA device.
old-location: display\dxva_coppcommand.htm
old-project: display
ms.assetid: 08c87f1f-ea50-4521-80a2-67369fc6598a
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*LPDXVA_COPPCommand, DXVA_COPPCommand, DXVA_COPPCommand structure [Display Devices], LPDXVA_COPPCommand, LPDXVA_COPPCommand structure pointer [Display Devices], _DXVA_COPPCommand, display.dxva_coppcommand, dxva/DXVA_COPPCommand, dxva/LPDXVA_COPPCommand, dxvaref_e27ea691-6ae9-41fc-9649-670231cb5ce8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: This structure applies only to Windows Server 2003 with SP1 and later, and Windows XP with SP2 and later.
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
-	dxva.h
apiname:
-	DXVA_COPPCommand
product: Windows
targetos: Windows
req.typenames: DXVA_COPPCommand, *LPDXVA_COPPCommand
---

# _DXVA_COPPCommand structure


## -description


The DXVA_COPPCommand structure describes a command sent to a protected video session that is associated with a COPP DirectX VA device.


## -syntax


````
typedef struct _DXVA_COPPCommand {
  GUID  macKDI;
  GUID  guidCommandID;
  ULONG dwSequence;
  ULONG cbSizeData;
  UCHAR CommandData[4056];
} DXVA_COPPCommand, *LPDXVA_COPPCommand;
````


## -struct-fields




### -field macKDI

Specifies a message authentication code (MAC) GUID for the command at <b>CommandData</b>. The display driver can use the MAC to verify that the transmission of the command was secure (that is, it was not tampered with in transit to the driver). 


### -field guidCommandID

Specifies the GUID that identifies the command. The following GUIDs are supported:





#### DXVA_COPPSetProtectionLevel

Sets the protection type and level on the physical connector associated with the COPP device.

The DXVA_COPPSetProtectionLevel GUID is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_GUID(DXVA_COPPSetProtectionLevel,
    0x9bb9327c,0x4eb5,0x4727,0x9f,0x00,0xb4,0x2b,0x09,0x19,0xc0,0xda);</pre>
</td>
</tr>
</table></span></div>


#### DXVA_COPPSetSignaling

An instruction about how to protect the signal that goes through the physical connector associated with the DirectX VA COPP device.

The DXVA_COPPSetSignaling GUID is defined as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>DEFINE_GUID(DXVA_COPPSetSignaling,
    0x9a631a5,0xd684,0x4c60,0x8e,0x4d,0xd3,0xbb,0xf,0xb,0xe3,0xee);</pre>
</td>
</tr>
</table></span></div>

### -field dwSequence

Specifies a sequence number. For the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539642">COPPCommand</a> function to process the command, the value in <b>dwSequence</b> must match the 32-bit random starting status sequence number that was passed in the <a href="..\dxva\ns-dxva-_dxva_coppsignature.md">DXVA_COPPSignature</a> structure to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540421">COPPSequenceStart</a> function.


### -field cbSizeData

Specifies the size, in bytes, of the command data at <b>CommandData</b>.


### -field CommandData

Specifies an array that comprises the command data. 


## -remarks



For a DXVA_COPPSetProtectionLevel command, the protection information is supplied in the first 16 bytes of the <b>CommandData</b> array (the protection type in the first 4 bytes, the protection level in the next 4 bytes, and possibly some extended information in the last 8 bytes). In the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539642">COPPCommand</a> function, the <b>CommandData</b> array should be cast to a pointer to a <a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a> structure, which contains protection type, protection level, and extended information members. 

For a DXVA_COPPSetSignaling command, the signaling information is supplied by casting the <b>CommandData</b> array to a pointer to a <a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a> structure. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539642">COPPCommand</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540421">COPPSequenceStart</a>



<a href="..\dxva\ns-dxva-_dxva_coppsetprotectionlevelcmddata.md">DXVA_COPPSetProtectionLevelCmdData</a>



<a href="..\dxva\ns-dxva-_dxva_coppsignature.md">DXVA_COPPSignature</a>



<a href="..\dxva\ns-dxva-_dxva_coppsetsignalingcmddata.md">DXVA_COPPSetSignalingCmdData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_COPPCommand structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

