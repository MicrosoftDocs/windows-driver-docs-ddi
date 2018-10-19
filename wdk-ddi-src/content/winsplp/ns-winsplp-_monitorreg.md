---
UID: NS:winsplp._MONITORREG
title: "_MONITORREG"
author: windows-driver-content
description: The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.
old-location: print\monitorreg.htm
tech.root: print
ms.assetid: 57c146bc-574f-4137-89bb-e891e005de05
ms.date: 04/20/2018
ms.keywords: "*PMONITORREG, MONITORREG, MONITORREG structure [Print Devices], PMONITORREG, PMONITORREG structure pointer [Print Devices], _MONITORREG, print.monitorreg, spoolfnc_2d0db8db-eea5-461a-a257-1fb986001dac.xml, winsplp/MONITORREG, winsplp/PMONITORREG"
ms.topic: struct
req.header: winsplp.h
req.include-header: Winsplp.h
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
-	winsplp.h
api_name:
-	MONITORREG
product:
- Windows
targetos: Windows
req.typenames: MONITORREG, *PMONITORREG
---

# _MONITORREG structure


## -description


The MONITORREG structure supplies print monitors with the address of registry functions to use instead of Win32 registry API functions.


## -struct-fields




### -field cbSize

Size, in bytes, of the MONITORREG structure.


### -field fpCreateKey


### -field fpOpenKey


### -field fpCloseKey


### -field fpDeleteKey


### -field fpEnumKey


### -field fpQueryInfoKey


### -field fpSetValue


### -field fpDeleteValue


### -field fpEnumValue


### -field fpQueryValue


## -remarks



The MONITORREG structure's address is supplied in a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557535">MONITORINIT</a> structure, which is passed to a print monitor's <a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a> function.

When <a href="https://msdn.microsoft.com/b1c83729-d7d2-4920-9402-4e00baa12633">storing port configuration information</a>, print monitors must not explicitly call either the Win32 registry API or the cluster registry API. Instead, they must call equivalent spooler registry functions. The MONITORREG structure supplies the addresses of these functions. The following table lists each spooler registry function and its equivalent cluster registry function.

<table>
<tr>
<th>Spooler Registry Function</th>
<th>Equivalent Cluster Registry Function</th>
</tr>
<tr>
<td>
<b>CreateKey</b>

</td>
<td>
<b>ClusterRegCreateKey</b>

</td>
</tr>
<tr>
<td>
<b>OpenKey</b>

</td>
<td>
<b>ClusterRegOpenKey</b>

</td>
</tr>
<tr>
<td>
<b>CloseKey</b>

</td>
<td>
<b>ClusterRegCloseKey</b>

</td>
</tr>
<tr>
<td>
<b>DeleteKey</b>

</td>
<td>
<b>ClusterRegDeleteKey</b>

</td>
</tr>
<tr>
<td>
<b>EnumKey</b>

</td>
<td>
<b>ClusterRegEnumKey</b>

</td>
</tr>
<tr>
<td>
<b>QueryInfoKey</b>

</td>
<td>
<b>ClusterRegQueryInfoKey</b>

</td>
</tr>
<tr>
<td>
<b>SetValue</b>

</td>
<td>
<b>ClusterRegSetValue</b>

</td>
</tr>
<tr>
<td>
<b>DeleteValue</b>

</td>
<td>
<b>ClusterRegDeleteValue</b>

</td>
</tr>
<tr>
<td>
<b>EnumValue</b>

</td>
<td>
<b>ClusterRegEnumValue</b>

</td>
</tr>
<tr>
<td>
<b>QueryValue</b>

</td>
<td>
<b>ClusterRegQueryValue</b>

</td>
</tr>
</table>
 

Input and output parameters for these spooler functions match the parameters of the equivalent cluster registry functions (described in the Microsoft Windows SDK documentation), with the following exceptions:

<ul>
<li>
Each spooler registry function requires an <i>hSpooler</i> input parameter. This is the spooler handle received in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557535">MONITORINIT</a> structure.

</li>
<li>
The spooler registry functions use HANDLE and PHANDLE parameter types instead of the HKEY and PHKEY types used by the cluster registry functions. Monitors receive the handle of the root registry location in the <b>hckRegistryRoot</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557535">MONITORINIT</a> structure.

</li>
</ul>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff551605">InitializePrintMonitor2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557535">MONITORINIT</a>
 

 

