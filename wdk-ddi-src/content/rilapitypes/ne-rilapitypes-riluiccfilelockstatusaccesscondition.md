---
UID: NE:rilapitypes.RILUICCFILELOCKSTATUSACCESSCONDITION
title: RILUICCFILELOCKSTATUSACCESSCONDITION
author: windows-driver-content
description: This enumeration describes the RILUICCFILELOCKSTATUSACCESSCONDITION.
old-location: netvista\riluiccfilelockstatusaccesscondition.htm
old-project: netvista
ms.assetid: 994bfab2-6bab-4aeb-87a9-a5b825efcb23
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILUICCFILELOCKSTATUSACCESSCONDITION, RILUICCFILELOCKSTATUSACCESSCONDITION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: Rilapitypes.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RILUICCFILELOCKSTATUSACCESSCONDITION
req.alt-loc: rilapitypes.h
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
req.typenames: RILUICCFILELOCKSTATUSACCESSCONDITION
req.product: Windows 10 or later.
---

# RILUICCFILELOCKSTATUSACCESSCONDITION enumeration



## -description

## -syntax

````
enum RILUICCFILELOCKSTATUSACCESSCONDITION {
  RIL_UICCFILEACCESSCONDITION_ALW   = 0x00, 
  RIL_UICCFILEACCESSCONDITION_PIN1  = 0x01, 
  RIL_UICCFILEACCESSCONDITION_PIN2  = 0x02, 
  RIL_UICCFILEACCESSCONDITION_RFU3  = 0x03, 
  RIL_UICCFILEACCESSCONDITION_RFU4  = 0x04, 
  RIL_UICCFILEACCESSCONDITION_ADM5  = 0x05, 
  RIL_UICCFILEACCESSCONDITION_ADM6  = 0x06, 
  RIL_UICCFILEACCESSCONDITION_NEV   = 0x07 

};
````


## -enum-fields

### -field RIL_UICCFILEACCESSCONDITION_ALW


### -field RIL_UICCFILEACCESSCONDITION_PIN1


### -field RIL_UICCFILEACCESSCONDITION_PIN2


### -field RIL_UICCFILEACCESSCONDITION_RFU3


### -field RIL_UICCFILEACCESSCONDITION_RFU4


### -field RIL_UICCFILEACCESSCONDITION_ADM5


### -field RIL_UICCFILEACCESSCONDITION_ADM6


### -field RIL_UICCFILEACCESSCONDITION_NEV


## -remarks


## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCFILELOCKSTATUSACCESSCONDITION enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

