---
UID: NF:spbcx.SpbRequestGetController
title: SpbRequestGetController function (spbcx.h)
description: The SpbRequestGetController method returns the WDFDEVICE handle to the device object for the SPB controller that the specified I/O request was sent to.
old-location: spb\spbrequestgetcontroller.htm
tech.root: SPB
ms.assetid: 0CD692E2-B2D6-4786-8C0B-C0DCAFCF6259
ms.date: 04/30/2018
ms.keywords: SPB.spbrequestgetcontroller, SpbRequestGetController, SpbRequestGetController method [Buses], spbcx/SpbRequestGetController
ms.topic: function
req.header: spbcx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Spbcxstubs.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- spbcxstubs.lib
- spbcxstubs.dll
api_name:
- SpbRequestGetController
product:
- Windows
targetos: Windows
req.typenames: 
---

# SpbRequestGetController function


## -description


The <b>SpbRequestGetController</b> method returns the WDFDEVICE handle to the device object for the SPB controller that the specified I/O request was sent to.


## -parameters




### -param SpbRequest [in]

The <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a> handle to the I/O request from which to retrieve the WDFDEVICE handle. The SPB controller driver previously received this handle through one of its registered <a href="https://docs.microsoft.com/previous-versions/hh450911(v=vs.85)">event callback functions</a>.


## -returns



<b>SpbRequestGetController</b> returns the WDFDEVICE handle that the I/O request was sent to.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>
 

 

