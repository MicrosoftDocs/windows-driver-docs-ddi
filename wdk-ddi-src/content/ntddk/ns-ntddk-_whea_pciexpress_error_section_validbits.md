---
UID: NS:ntddk._WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
title: "_WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS"
author: windows-driver-content
description: The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a WHEA_PCIEXPRESS_ERROR_SECTION structure contain valid data.
old-location: whea\whea_pciexpress_error_section_validbits.htm
old-project: whea
ms.assetid: 1c4c3e9c-32a2-405a-b27d-98f8da715626
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ntddk/PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIEXPRESS_ERROR_VALIDBITS, WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union [WHEA Drivers and Applications], *PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, whea.whea_pciexpress_error_section_validbits, WHEA_PCIEXPRESS_ERROR_VALIDBITS, _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, whearef_9b6e3f92-4939-401a-9da2-e2ece44b1e98.xml, WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union pointer [WHEA Drivers and Applications], ntddk/WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Windows
req.target-min-winverclnt: Supported in Windows Server 2008, Windows Vista SP1, and later versions of Windows.
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS
product: Windows
targetos: Windows
req.typenames: "*PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS"
---

# _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS structure


## -description


The WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union describes which members of a <a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure contain valid data.


## -syntax


````
typedef union _WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS {
  struct {
    ULONGLONG PortType  :1;
    ULONGLONG Version  :1;
    ULONGLONG CommandStatus  :1;
    ULONGLONG DeviceId  :1;
    ULONGLONG DeviceSerialNumber  :1;
    ULONGLONG BridgeControlStatus  :1;
    ULONGLONG ExpressCapability  :1;
    ULONGLONG AerInfo  :1;
    ULONGLONG Reserved  :56;
  };
  ULONGLONG ValidBits;
} WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS, *PWHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS;
````


## -struct-fields




### -field DUMMYSTRUCTNAME

 


### -field ValidBits

A ULONGLONG representation of the contents of the WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union.


#### - PortType

A single bit that indicates that the <b>PortType</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - Version

A single bit that indicates that the <b>Version</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - CommandStatus

A single bit that indicates that the <b>CommandStatus</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - DeviceId

A single bit that indicates that the <b>DeviceId</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - DeviceSerialNumber

A single bit that indicates that the <b>DeviceSerialNumber</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - BridgeControlStatus

A single bit that indicates that the <b>BridgeControlStatus</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - ExpressCapability

A single bit that indicates that the <b>ExpressCapability</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - AerInfo

A single bit that indicates that the <b>AerInfo</b> member of the WHEA_PCIEXPRESS_ERROR_SECTION structure contains valid data.


#### - Reserved

Reserved for system use.


## -remarks



A WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union is contained within the <a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a> structure.




## -see-also

<a href="..\ntddk\ns-ntddk-_whea_pciexpress_error_section.md">WHEA_PCIEXPRESS_ERROR_SECTION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [whea\whea]:%20WHEA_PCIEXPRESS_ERROR_SECTION_VALIDBITS union%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

