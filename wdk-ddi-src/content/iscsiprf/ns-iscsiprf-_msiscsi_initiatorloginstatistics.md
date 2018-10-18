---
UID: NS:iscsiprf._MSiSCSI_InitiatorLoginStatistics
title: "_MSiSCSI_InitiatorLoginStatistics"
author: windows-driver-content
description: The MSiSCSI_InitiatorLoginStatistics structure is used by iSCSI initiators to report logon statistics.
old-location: storage\msiscsi_initiatorloginstatistics.htm
tech.root: storage
ms.assetid: 8d670887-e8bb-4b99-99ae-16c0dd9c4431
ms.date: 03/29/2018
ms.keywords: "*PMSiSCSI_InitiatorLoginStatistics, MSiSCSI_InitiatorLoginStatistics, MSiSCSI_InitiatorLoginStatistics structure [Storage Devices], PMSiSCSI_InitiatorLoginStatistics, PMSiSCSI_InitiatorLoginStatistics structure pointer [Storage Devices], _MSiSCSI_InitiatorLoginStatistics, iscsiprf/MSiSCSI_InitiatorLoginStatistics, iscsiprf/PMSiSCSI_InitiatorLoginStatistics, storage.msiscsi_initiatorloginstatistics, structs-iSCSI_a19b84b5-d660-4005-a22d-2d4157eadab9.xml"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	iscsiprf.h
api_name:
-	MSiSCSI_InitiatorLoginStatistics
product:
- Windows
targetos: Windows
req.typenames: MSiSCSI_InitiatorLoginStatistics, *PMSiSCSI_InitiatorLoginStatistics
---

# _MSiSCSI_InitiatorLoginStatistics structure


## -description


The MSiSCSI_InitiatorLoginStatistics structure is used by iSCSI initiators to report logon statistics. 


## -struct-fields




### -field UniqueAdapterId

A 64-bit integer that uniquely identifies an HBA initiator and a loaded instance of a storage miniport driver that manages the HBA. The initiator should use the address of the adapter extension or another address that the device driver owns to construct this identifier (ID). The initiator reports this value in the <b>UniqueAdapterId</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a> structure.


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




<a href="https://msdn.microsoft.com/library/windows/hardware/ff563012">MSiSCSI_HBAInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563042">MSiSCSI_InitiatorLoginStatistics WMI Class</a>
 

 

