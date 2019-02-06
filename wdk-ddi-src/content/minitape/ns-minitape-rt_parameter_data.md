---
UID: NS:minitape.__unnamed_struct_13
title: RT_PARAMETER_DATA (minitape.h)
description: The RT_PARAMETER_DATA structure contains the parameter data for the report timestamp command.
old-location: storage\rt_parameter_data.htm
tech.root: storage
ms.assetid: EB23D502-87E4-48B1-B1DC-0B215AB361C8
ms.date: 03/29/2018
ms.keywords: "*PRT_PARAMETER_DATA, PRT_PARAMETER_DATA, PRT_PARAMETER_DATA structure pointer [Storage Devices], RT_PARAMETER_DATA, RT_PARAMETER_DATA structure [Storage Devices], scsi/PRT_PARAMETER_DATA, scsi/RT_PARAMETER_DATA, storage.rt_parameter_data"
ms.topic: struct
req.header: minitape.h
req.include-header: Minitape.h, Storport.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 10, version 1709 and later versions of Windows.
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
-	scsi.h
api_name:
-	RT_PARAMETER_DATA
product:
- Windows
targetos: Windows
req.typenames: RT_PARAMETER_DATA, *PRT_PARAMETER_DATA
---

# RT_PARAMETER_DATA structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>RT_PARAMETER_DATA</b> structure contains the parameter data for the report timestamp command. 


## -struct-fields




### -field ParameterDataLength

Indicates the number of bytes that follow in the parameter data.


### -field Origin

Indicates the most recent event that initialized the returned device clock.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>0</dt>
</dl>
</td>
<td width="60%">
Device clock initialized to zero at power on or as the result of a hard reset.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>1</dt>
</dl>
</td>
<td width="60%">
Reserved for future use.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>2</dt>
</dl>
</td>
<td width="60%">
Device clock initialized by the SET TIMESTAMP command.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>3</dt>
</dl>
</td>
<td width="60%">
Device clock initialized by an unknown method.

</td>
</tr>
<tr>
<td width="40%"><a id=""></a><dl>
<dt><b></b></dt>
<dt>4 to 7</dt>
</dl>
</td>
<td width="60%">
Reserved for future use.

</td>
</tr>
</table>
 


### -field Reserved1

Reserved for future use.


### -field Reserved2

Reserved for future use.


### -field Timestamp

Contains the current value of a device clock.


### -field Reserved3

Reserved for future use.


## -see-also




<a href="https://msdn.microsoft.com/C50F45EC-433C-421D-BD02-4C86CB44D5A4">ST_PARAMETER_DATA</a>
 

 

