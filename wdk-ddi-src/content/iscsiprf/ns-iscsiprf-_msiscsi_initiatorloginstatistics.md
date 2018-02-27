---
UID: NS:iscsiprf._MSiSCSI_InitiatorLoginStatistics
title: "_MSiSCSI_InitiatorLoginStatistics"
author: windows-driver-content
description: The MSiSCSI_InitiatorLoginStatistics structure is used by iSCSI initiators to report logon statistics.
old-location: storage\msiscsi_initiatorloginstatistics.htm
old-project: storage
ms.assetid: 8d670887-e8bb-4b99-99ae-16c0dd9c4431
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PMSiSCSI_InitiatorLoginStatistics, MSiSCSI_InitiatorLoginStatistics, MSiSCSI_InitiatorLoginStatistics structure [Storage Devices], PMSiSCSI_InitiatorLoginStatistics, PMSiSCSI_InitiatorLoginStatistics structure pointer [Storage Devices], _MSiSCSI_InitiatorLoginStatistics, iscsiprf/MSiSCSI_InitiatorLoginStatistics, iscsiprf/PMSiSCSI_InitiatorLoginStatistics, storage.msiscsi_initiatorloginstatistics, structs-iSCSI_a19b84b5-d660-4005-a22d-2d4157eadab9.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: iscsiprf.h
req.include-header: Iscsiprf.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	iscsiprf.h
apiname:
-	MSiSCSI_InitiatorLoginStatistics
product: Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorLoginStatistics, *PMSiSCSI_InitiatorLoginStatistics
---

# _MSiSCSI_InitiatorLoginStatistics structure


## -description


The MSiSCSI_InitiatorLoginStatistics structure is used by iSCSI initiators to report logon statistics. 


## -syntax


````
typedef struct _MSiSCSI_InitiatorLoginStatistics {
  ULONGLONG UniqueAdapterId;
  ULONG     LoginAcceptRsps;
  ULONG     LoginOtherFailRsps;
  ULONG     LoginRedirectRsps;
  ULONG     LoginAuthFailRsps;
  ULONG     LoginAuthenticateFails;
  ULONG     LoginNegotiateFails;
  ULONG     LogoutNormals;
  ULONG     LogoutOtherCodes;
  ULONG     LoginFailures;
} MSiSCSI_InitiatorLoginStatistics, *PMSiSCSI_InitiatorLoginStatistics;
````


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a> structure.


### -field LoginAcceptRsps

The number of login accept responses. 


### -field LoginOtherFailRsps

The number of failed responses.


### -field LoginRedirectRsps

The number of redirect responses.


### -field LoginAuthFailRsps

The number of logon responses that failed because the initiator and target did not have compatible authentication algorithms.


### -field LoginAuthenticateFails

The number of logons that failed because of a target authentication failure (the initiator and target did not have matching credentials).


### -field LoginNegotiateFails

The number of logons that failed because of negotiation failures.


### -field LogoutNormals

The number of logoff PDUs with a reason code of 0.


### -field LogoutOtherCodes

The number of logoff PDUs with a status code other than 0.


### -field LoginFailures

The number of times that a logon attempt by the initiator has failed.


## -remarks



It is optional that you implement this class.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563042">MSiSCSI_InitiatorLoginStatistics WMI Class</a>



<a href="..\iscsimgt\ns-iscsimgt-_msiscsi_hbainformation.md">MSiSCSI_HBAInformation</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20MSiSCSI_InitiatorLoginStatistics structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

