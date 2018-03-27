---
UID: NS:61883._UNIT_DIAG_LEVEL
title: "_UNIT_DIAG_LEVEL"
author: windows-driver-content
description: The UNIT_DDI_VERSION structure is used in conjunction with the Av61883_GetUnitInfo request to retrieve the current diag level
old-location: ieee\unit_diag_level.htm
old-project: IEEE
ms.assetid: 2759486f-7eaa-4af4-b9a9-2e44354f411b
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PUNIT_DIAG_LEVEL, 61883/PUNIT_DIAG_LEVEL, 61883/UNIT_DIAG_LEVEL, 61883_structures_02b60b1d-45d1-474b-901c-4346b23c8d25.xml, IEEE.unit_diag_level, PUNIT_DIAG_LEVEL, PUNIT_DIAG_LEVEL structure pointer [Buses], UNIT_DIAG_LEVEL, UNIT_DIAG_LEVEL structure [Buses], _UNIT_DIAG_LEVEL"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: 61883.h
req.include-header: 61883.h
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
-	61883.h
api_name:
-	UNIT_DIAG_LEVEL
product: Windows
targetos: Windows
req.typenames: UNIT_DIAG_LEVEL, *PUNIT_DIAG_LEVEL
---

# _UNIT_DIAG_LEVEL structure


## -description


The UNIT_DDI_VERSION structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a> request to retrieve the current diag level 


## -struct-fields




### -field DiagLevel

The bitmask representing the diaglevel. Possible settings are:





#### DIAGLEVEL_NONE

Nothing set.



#### DIAGLEVEL_IGNORE_OPLUG

Ignore programming of the oPCR plug on the device when set.



#### DIAGLEVEL_IGNORE_IPLUG

Ignore programming of the iPCR on the device when set.



#### DIAGLEVEL_SET_CHANNEL_63

Set the channel to 63 when disconnecting from the device.



#### DIAGLEVEL_IPCR_IGNORE_FREE

Do not free isochronous resources when disconnecting from the device iPCR.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536983">Av61883_GetUnitInfo</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [IEEE\buses]:%20UNIT_DIAG_LEVEL structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

