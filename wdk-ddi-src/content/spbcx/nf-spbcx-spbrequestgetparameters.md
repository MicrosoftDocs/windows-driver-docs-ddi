---
UID: NF:spbcx.SpbRequestGetParameters
title: SpbRequestGetParameters function
author: windows-driver-content
description: The SpbRequestGetParameters method retrieves a set of SPB-specific parameter values from an I/O request.
old-location: spb\spbrequestgetparameters.htm
tech.root: SPB
ms.assetid: 676C28C4-E6F3-4190-927B-67D5618F5645
ms.date: 04/30/2018
ms.keywords: SPB.spbrequestgetparameters, SpbRequestGetParameters, SpbRequestGetParameters method [Buses], spbcx/SpbRequestGetParameters
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
-	SpbRequestGetParameters
product:
- Windows
targetos: Windows
req.typenames: 
---

# SpbRequestGetParameters function


## -description


The <b>SpbRequestGetParameters</b> method retrieves a set of SPB-specific parameter values from an I/O request.


## -parameters




### -param SpbRequest [in]

An <a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>  handle to the I/O request. The SPB controller driver previously received this handle through one of its registered <a href="https://msdn.microsoft.com/1DA1FF41-FB01-45CC-B0C1-EAF2C81D0CDA">event callback functions</a>.


### -param Parameters [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/91A5C504-7072-4B64-86F1-2BDE616CCA31">SPB_REQUEST_PARAMETERS</a> structure into which the method writes the SPB-specific parameter values from the I/O request. The caller must have previously initialized this structure by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406210">SPB_REQUEST_PARAMETERS_INIT</a> function.


## -returns



None.




## -remarks



<b>SpbRequestGetParameters</b> is similar to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a> method, but retrieves only SPB-specific information. Your SPB controller driver can call  <b>SpbRequestGetParameters</b> to retrieve SPB-specific information from I/O requests that it receives from the SPB framework extension (SpbCx). The SPB controller driver can call <b>WdfRequestGetParameters</b> to retrieve the generic request parameters from I/O requests that it receives.


#### Examples

The following code example shows how to use <b>SpbRequestGetParameters</b> to retrieve the SPB-specific parameters from an I/O request. The  <i>spbRequest</i> variable contains an SPBREQUEST handle to the I/O request.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>SPB_REQUEST_PARAMETERS parameters;

SPB_REQUEST_PARAMETERS_INIT(&amp;parameters);

SpbRequestGetParameters(spbRequest, &amp;parameters);

</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/spb/spbcx-object-handles">SPBREQUEST</a>



<a href="https://msdn.microsoft.com/91A5C504-7072-4B64-86F1-2BDE616CCA31">SPB_REQUEST_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406210">SPB_REQUEST_PARAMETERS_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549969">WdfRequestGetParameters</a>
 

 

