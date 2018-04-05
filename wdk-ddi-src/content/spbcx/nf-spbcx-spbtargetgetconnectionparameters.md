---
UID: NF:spbcx.SpbTargetGetConnectionParameters
title: SpbTargetGetConnectionParameters function
author: windows-driver-content
description: The SpbTargetGetConnectionParameters method retrieves the connection parameters for a target device on the bus.
old-location: spb\spbtargetgetconnectionparameters.htm
old-project: SPB
ms.assetid: 0692D8A3-CA43-4D27-9E8E-EB104DB1651F
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: SPB.spbtargetgetconnectionparameters, SpbTargetGetConnectionParameters, SpbTargetGetConnectionParameters method [Buses], spbcx/SpbTargetGetConnectionParameters
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	spbcxstubs.lib
-	spbcxstubs.dll
api_name:
-	SpbTargetGetConnectionParameters
product:
- Windows
targetos: Windows
req.typenames: SPB_REQUEST_TYPE, *PSPB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# SpbTargetGetConnectionParameters function


## -description


The <b>SpbTargetGetConnectionParameters</b> method retrieves the connection parameters for a target device on the bus.


## -parameters




### -param Target [in]

An <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a> handle to the target device for which to retrieve the connection parameters.


### -param ConnectionParameters [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a> structure into which the method writes the connection parameters. The caller must previously have called the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406205">SPB_CONNECTION_PARAMETERS_INIT</a> function to initialize this structure.


## -returns



None.




## -remarks



This method retrieves a set of connection parameters that the SPB controller driver requires to access the specified target device on the bus. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a>.

A client (peripheral driver) that successfully opens a connection to a target has exclusive use of that target.

The SPB framework extension (SpbCx) calls your controller driver's <a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a> and <a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a> callback functions to open and close a connection.

<b>SpbTargetGetConnectionParameters</b> will not fail if it is called with a valid SPBTARGET handle.




## -see-also




<a href="https://msdn.microsoft.com/D90DD169-A989-4D08-B1B8-BDE7EC9B7A82">EvtSpbTargetConnect</a>



<a href="https://msdn.microsoft.com/02756C35-E76C-42C0-80FA-359CADE224A1">EvtSpbTargetDisconnect</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/spb/spbcx-object-handles">SPBTARGET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406204">SPB_CONNECTION_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406205">SPB_CONNECTION_PARAMETERS_INIT</a>
 

 

