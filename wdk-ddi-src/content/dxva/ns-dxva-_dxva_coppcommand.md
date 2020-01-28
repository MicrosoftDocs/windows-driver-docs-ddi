---
UID: NS:dxva._DXVA_COPPCommand
title: _DXVA_COPPCommand (dxva.h)
description: The DXVA_COPPCommand structure describes a command sent to a protected video session that is associated with a COPP DirectX VA device.
old-location: display\dxva_coppcommand.htm
tech.root: display
ms.assetid: 08c87f1f-ea50-4521-80a2-67369fc6598a
ms.date: 05/10/2018
ms.keywords: "*LPDXVA_COPPCommand, DXVA_COPPCommand, DXVA_COPPCommand structure [Display Devices], LPDXVA_COPPCommand, LPDXVA_COPPCommand structure pointer [Display Devices], _DXVA_COPPCommand, display.dxva_coppcommand, dxva/DXVA_COPPCommand, dxva/LPDXVA_COPPCommand, dxvaref_e27ea691-6ae9-41fc-9649-670231cb5ce8.xml"
f1_keywords:
 - "dxva/DXVA_COPPCommand"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- dxva.h
api_name:
- DXVA_COPPCommand
product:
- Windows
targetos: Windows
req.typenames: DXVA_COPPCommand, *LPDXVA_COPPCommand
---

# _DXVA_COPPCommand structure


## -description


The DXVA_COPPCommand structure describes a command sent to a protected video session that is associated with a COPP DirectX VA device.


## -struct-fields




### -field macKDI

Specifies a message authentication code (MAC) GUID for the command at <b>CommandData</b>. The display driver can use the MAC to verify that the transmission of the command was secure (that is, it was not tampered with in transit to the driver). 


### -field guidCommandID

Specifies the GUID that identifies the command. The following GUIDs are supported:





#### DXVA_COPPSetProtectionLevel

Sets the protection type and level on the physical connector associated with the COPP device.

The DXVA_COPPSetProtectionLevel GUID is defined as follows:

```cpp
DEFINE_GUID(DXVA_COPPSetProtectionLevel,
    0x9bb9327c,0x4eb5,0x4727,0x9f,0x00,0xb4,0x2b,0x09,0x19,0xc0,0xda);
```

#### DXVA_COPPSetSignaling

An instruction about how to protect the signal that goes through the physical connector associated with the DirectX VA COPP device.

The DXVA_COPPSetSignaling GUID is defined as follows:

```cpp
DEFINE_GUID(DXVA_COPPSetSignaling,
    0x9a631a5,0xd684,0x4c60,0x8e,0x4d,0xd3,0xbb,0xf,0xb,0xe3,0xee);
```

### -field dwSequence

Specifies a sequence number. For the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppcommand">COPPCommand</a> function to process the command, the value in <b>dwSequence</b> must match the 32-bit random starting status sequence number that was passed in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsignature">DXVA_COPPSignature</a> structure to the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppsequencestart">COPPSequenceStart</a> function.


### -field cbSizeData

Specifies the size, in bytes, of the command data at <b>CommandData</b>.


### -field CommandData

Specifies an array that comprises the command data. 


## -remarks



For a DXVA_COPPSetProtectionLevel command, the protection information is supplied in the first 16 bytes of the <b>CommandData</b> array (the protection type in the first 4 bytes, the protection level in the next 4 bytes, and possibly some extended information in the last 8 bytes). In the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppcommand">COPPCommand</a> function, the <b>CommandData</b> array should be cast to a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsetprotectionlevelcmddata">DXVA_COPPSetProtectionLevelCmdData</a> structure, which contains protection type, protection level, and extended information members. 

For a DXVA_COPPSetSignaling command, the signaling information is supplied by casting the <b>CommandData</b> array to a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsetsignalingcmddata">DXVA_COPPSetSignalingCmdData</a> structure. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppcommand">COPPCommand</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/display/coppsequencestart">COPPSequenceStart</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsetprotectionlevelcmddata">DXVA_COPPSetProtectionLevelCmdData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsetsignalingcmddata">DXVA_COPPSetSignalingCmdData</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxva/ns-dxva-_dxva_coppsignature">DXVA_COPPSignature</a>
 

 

