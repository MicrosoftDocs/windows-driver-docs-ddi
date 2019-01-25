---
UID: NF:ucxcontroller.UcxControllerNotifyTransportCharacteristicsChange
title: UcxControllerNotifyTransportCharacteristicsChange function (ucxcontroller.h)
description: Notifies UCX about a new port change event from host controller.
old-location: buses\ucxcontrollernotifytransportcharacteristicschange.htm
tech.root: usbref
ms.assetid: DB49DF98-8A5B-4528-B312-63CE3DFABEF2
ms.date: 05/07/2018
ms.keywords: UcxControllerNotifyTransportCharacteristicsChange, UcxControllerNotifyTransportCharacteristicsChange function [Buses], buses.ucxcontrollernotifytransportcharacteristicschange, ucxcontroller/UcxControllerNotifyTransportCharacteristicsChange
ms.topic: function
req.header: ucxcontroller.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ucxstubs.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Ucxstubs.lib
-	Ucxstubs.dll
api_name:
-	UcxControllerNotifyTransportCharacteristicsChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# UcxControllerNotifyTransportCharacteristicsChange function


## -description


Notifies UCX about a new port change event from host controller.



## -parameters




### -param Controller

<p> A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/Mt188033(v=VS.85).aspx"><b>UcxControllerCreate</b></a> method.</p>


### -param UcxControllerTransportCharacteristics [out]

A pointer to a <a href="https://msdn.microsoft.com/9F267427-8D70-45D5-A8E6-67A1C6B73CDB">UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS</a> structure that contains the updated transport characteristics.


## -returns



This function does not return a value.




## -see-also




<a href="https://msdn.microsoft.com/4394199C-6644-4E11-BDAF-625C2F94DEE8">EVT_UCX_CONTROLLER_GET_TRANSPORT_CHARACTERISTICS</a>
 

 

