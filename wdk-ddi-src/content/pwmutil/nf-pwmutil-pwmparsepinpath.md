---
UID: NF:pwmutil.PwmParsePinPath
title: PwmParsePinPath function (pwmutil.h)
description: Parses a pin path under the Pulse Width Modulation (PWM) controller namespace to validate its format and extract the pin number.
old-location: kernel\pwmparsepinpath.htm
tech.root: spb
ms.assetid: 854A2B6F-A841-4AE4-9E54-68EF048C9504
ms.date: 04/30/2018
keywords: ["PwmParsePinPath function"]
ms.keywords: PwmParsePinPath, PwmParsePinPath function [Kernel-Mode Driver Architecture], kernel.pwmparsepinpath, pwmutil/PwmParsePinPath
f1_keywords:
 - "pwmutil/PwmParsePinPath"
 - "PwmParsePinPath"
req.header: pwmutil.h
req.include-header: Pwm.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.19
req.umdf-ver: 2.19
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- PwmParsePinPath
targetos: Windows
req.typenames: 
---

# PwmParsePinPath function


## -description


Parses a pin path under the Pulse Width Modulation (PWM) controller namespace to validate its format and extract the pin number.


## -parameters




### -param PinPath 
[in]
A pointer to pin path as a Unicode character string.


### -param PinNumber 
[out, optional]
A pointer to variable that receives a pin number.


## -returns



<b>PwmParsePinPath</b> returns the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
Extracted pin path successfully from supplied pin path.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The specified pin path pointer is invalid or its Unicode string is
        invalid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NO_SUCH_FILE</b></dt>
</dl>
</td>
<td width="60%">
 The specified pin path does not constitute a valid pin path.

</td>
</tr>
</table>
 




## -remarks



The pin path must be a Unicode character string that ends in the pin number as follows: <i>...\<PinNumber></i>.



