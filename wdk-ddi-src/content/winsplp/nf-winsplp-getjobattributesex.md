---
UID: NF:winsplp.GetJobAttributesEx
title: GetJobAttributesEx function
author: windows-driver-content
description: Warning  Starting with Windows 10, the APIs which support third-party print providers are deprecated.
old-location: print\getjobattributesex.htm
old-project: print
ms.assetid: 0715e4d4-665c-42cb-9c74-48c2c558c277
ms.author: windowsdriverdev
ms.date: 4/20/2018
ms.keywords: GetJobAttributesEx, GetJobAttributesEx function [Print Devices], print.getjobattributesex, spoolfnc_45659d86-d97e-47c5-bbf7-49c990880b52.xml, winsplp/GetJobAttributesEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: Winsplp.h
req.target-type: Desktop
req.target-min-winverclnt: This function is available in the Windows Vista operating system.
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
req.lib: Spoolss.lib
req.dll: Spoolss.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	Spoolss.dll
api_name:
-	GetJobAttributesEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# GetJobAttributesEx function


## -description


<div class="alert"><b>Warning</b>  <p class="note">Starting with Windows 10, the APIs which support third-party print providers are deprecated. Microsoft does not recommend any investment into third-party print providers. Additionally, on Windows 8 and newer products where the v4 print driver model is available, third-party print providers may not create or manage queues which use v4 print drivers.

</div><div> </div>A print provider's <b>GetJobAttributesEx</b> function obtains information about a print job, including N-up and reverse printing options.


## -parameters




### -param pPrinterName [in]

Caller-supplied pointer to a NULL-terminated Unicode string that contains the printer name.


### -param pDevmode [in]

Caller-supplied pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a> structure that is passed to the print processor or printer driver.


### -param dwLevel [in]

Caller-supplied value that indicates the type of structure pointed to by <i>pAttributeInfo</i>, as indicated in the following table. For more information, see Remarks.

<table>
<tr>
<th><i>dwLevel</i> Value</th>
<th>Structure pointed to by <i>pAttributeInfo</i></th>
</tr>
<tr>
<td>
1

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>


</td>
</tr>
<tr>
<td>
2

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545091">ATTRIBUTE_INFO_2</a>


</td>
</tr>
<tr>
<td>
3

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a>


</td>
</tr>
<tr>
<td>
4

</td>
<td>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>


</td>
</tr>
</table>
 


### -param pAttributeInfo [out]

Caller-supplied pointer to an attribute information structure (<a href="https://msdn.microsoft.com/library/windows/hardware/ff545090">ATTRIBUTE_INFO_1</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545091">ATTRIBUTE_INFO_2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>) that receives information about the print job.


### -param nSize [in]

Size of the buffer, in bytes, pointed to by <i>pAttributeInfo</i>.


### -param dwFlags [in]

If set by the caller to FILL_WITH_DEFAULTS, then the spooler will fill <i>pAttributeInfo</i> with default values from level 1 up to the level specified by <i>dwLevel</i>.

For example, if <i>dwLevel</i> is 4 and FILL_WITH_DEFAULTS is specified, <i>pAttributeInfo</i> will be filled with the following default member values of <a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>:

<b>dwJobNumberOfPagesPerSide</b> = 1

<b>dwDrvNumberOfPagesPerSide</b> = 1

<b>dwNupBorderFlags</b> = 0

<b>dwJobPageOrderFlags</b> = 0

<b>dwDrvPageOrderFlags</b> = 0

<b>dwJobNumberOfCopies</b> = <b>dmCopies</b> member of <a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>


<b>dwDrvNumberOfCopies</b>  = <b>dmCopies</b> member of DEVMODEW

<b>dwColorOptimization</b> = 0

<b>dmPrintQuality</b> = <b>dmPrintQuality</b> member of DEVMODEW

<b>dmYResolution</b> = <b>dmYResolution</b> member of DEVMODEW

<b>dwNupDirection</b> = RIGHT_THEN_DOWN

<b>dwBookletFlags </b>= BOOKLET_EDGE_LEFT

<b>dwDuplexFlags </b>= 0

<b>dwScalingPercentX </b>= 100

<b>dwScalingPercentY </b>= 100

<b>dwJobHandlingFlags </b>= 0

See Remarks.


## -returns



<b>GetJobAttributesEx</b> returns <b>TRUE</b> if it is successful in obtaining the print job attributes; otherwise, it returns <b>FALSE</b>.




## -remarks



This function first checks whether the driver supports the attribute level that is indicated by <i>dwLevel</i>. If the driver does not support that attribute level, then the function queries the driver for support for the next lower level, (<i>dwLevel</i> - 1), and continues to query for progressively lower levels of support until it obtains the level of support provided by the driver. If <i>dwFlags</i> is set to FILL_WITH_DEFAULTS, then the function fills in the default values for the unsupported levels.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545093">ATTRIBUTE_INFO_3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545096">ATTRIBUTE_INFO_4</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552837">DEVMODEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550456">GetJobAttributes</a>
 

 

