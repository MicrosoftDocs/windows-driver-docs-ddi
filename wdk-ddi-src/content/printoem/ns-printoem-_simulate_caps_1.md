---
UID: NS:printoem._SIMULATE_CAPS_1
title: "_SIMULATE_CAPS_1"
author: windows-driver-content
description: The SIMULATE_CAPS_1 structure contains information about the types of simulations a spooler supports.
old-location: print\simulate_caps_1.htm
old-project: print
ms.assetid: 17f5d8bf-a3e7-4ff5-9019-24c66875b786
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: PSIMULATE_CAPS_1 structure pointer [Print Devices], print_interface-graphics_cb1ba0de-be04-4b11-a746-97fd3f2bc213.xml, SIMULATE_CAPS_1 structure [Print Devices], SIMULATE_CAPS_1, *PSIMULATE_CAPS_1, PSIMULATE_CAPS_1, _SIMULATE_CAPS_1, printoem/SIMULATE_CAPS_1, printoem/PSIMULATE_CAPS_1, print.simulate_caps_1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: printoem.h
req.include-header: Printoem.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	printoem.h
apiname:
-	SIMULATE_CAPS_1
product: Windows
targetos: Windows
req.typenames: SIMULATE_CAPS_1, *PSIMULATE_CAPS_1
req.product: Windows 10 or later.
---

# _SIMULATE_CAPS_1 structure


## -description


The SIMULATE_CAPS_1 structure contains information about the types of simulations a spooler supports.


## -syntax


````
typedef struct _SIMULATE_CAPS_1 {
  DWORD dwLevel;
  DWORD dwPageOrderFlags;
  DWORD dwNumberOfCopies;
  DWORD dwCollate;
  DWORD dwNupOptions;
} SIMULATE_CAPS_1, *PSIMULATE_CAPS_1;
````


## -struct-fields




### -field dwLevel

Specifies the version of this structure. This value must be 1.


### -field dwPageOrderFlags

Specifies the order in which pages will be printed. This member can be set to one of the following values:
<table>
<tr>
<th>Flag</th>
<th>Definition</th>
</tr>
<tr>
<td>
BOOKLET_PRINT

</td>
<td>
Pages should be printed in booklet form, with two document pages printed on one side of a physical page. In landscape mode, the two document pages are printed side-by-side on the paper. In portrait mode, the two document pages are printed top-and-bottom.

</td>
</tr>
<tr>
<td>
NORMAL_PRINT

</td>
<td>
Pages should be printed in normal order: page 1, page 2, and so on.

</td>
</tr>
<tr>
<td>
REVERSE_PRINT

</td>
<td>
Pages should be printed in reverse order: last page, next-to-last page, and so on.

</td>
</tr>
</table> 


### -field dwNumberOfCopies

Specifies the maximum number of copies the spooler can handle.


### -field dwCollate

Specifies whether the spooler supports collation. A value of 1 indicates that the spooler supports collation, and a value of 0 indicates that it does not.


### -field dwNupOptions

Is a bitmask representing the various numbers of document pages the printer can print on a physical page. The least significant bit represents 1 document page per page, the next bit represents 2 document pages per page, the next bit represents 3 document pages per physical page, and so on. For example, 0x0000810B indicates that the spooler supports 1, 2, 4, 9, and 16 document pages per physical page.


## -remarks


The <b>IPrintCoreUI2::QuerySimulationSupport</b> method uses this structure to report the spooler's level of simulation support to a user-interface plug-in.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff553074">IPrintCoreUI2::QuerySimulationSupport</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [print\print]:%20SIMULATE_CAPS_1 structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

