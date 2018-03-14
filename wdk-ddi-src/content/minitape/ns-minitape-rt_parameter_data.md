---
UID: NS:minitape.RT_PARAMETER_DATA
title: RT_PARAMETER_DATA
author: windows-driver-content
description: The RT_PARAMETER_DATA structure contains the parameter data for the report timestamp command.
old-location: storage\rt_parameter_data.htm
old-project: storage
ms.assetid: EB23D502-87E4-48B1-B1DC-0B215AB361C8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PRT_PARAMETER_DATA, PRT_PARAMETER_DATA, PRT_PARAMETER_DATA structure pointer [Storage Devices], RT_PARAMETER_DATA, RT_PARAMETER_DATA structure [Storage Devices], scsi/PRT_PARAMETER_DATA, scsi/RT_PARAMETER_DATA, storage.rt_parameter_data"
ms.prod: windows-hardware
ms.technology: windows-devices
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
product: Windows
targetos: Windows
req.typenames: RT_PARAMETER_DATA, *PRT_PARAMETER_DATA
---

# RT_PARAMETER_DATA structure


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>RT_PARAMETER_DATA</b> structure contains the parameter data for the report timestamp command. 


## -syntax


````
typedef struct _RT_PARAMETER_DATA {
  UCHAR     ParameterDataLength[2];
  UCHAR Origin  :3;
  UCHAR Reserved1  :5;
  UCHAR Reserved2;
  UCHAR Timestamp[6];
  UCHAR Reserved3[2];
} RT_PARAMETER_DATA, *PRT_PARAMETER_DATA;
````


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

<a href="..\storport\ns-storport-st_parameter_data.md">ST_PARAMETER_DATA</a>



 

 


