---
UID: NF:engextcpp.ExtRemoteData.Write
title: ExtRemoteData::Write method
author: windows-driver-content
description: The Write method writes the data cached by the ExtRemoteData object to the region of memory on the target, represented by this object.
old-location: debugger\extremotedata_write.htm
old-project: debugger
ms.assetid: 970c725b-4ea0-42b7-a373-83cb463cd80d
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: debugger.extremotedata_write, ExtRemoteData, Write method [Windows Debugging], ExtRemoteData class, ExtRemoteData class [Windows Debugging], Write method, EngExtCpp_Ref_1288bed4-2f61-4af4-a226-5157a0622f42.xml, Write, Write method [Windows Debugging], ExtRemoteData::Write
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: engextcpp.hpp
req.include-header: Engextcpp.hpp
req.target-type: Desktop
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
req.lib: engextcpp.hpp
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	engextcpp.hpp
apiname:
-	ExtRemoteData.Write
product: Windows
targetos: Windows
req.typenames: SILO_DRIVER_CAPABILITIES, *PSILO_DRIVER_CAPABILITIES
---

# ExtRemoteData::Write method


## -description


The <b>Write</b> method writes the data cached by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object to the region of memory on the target, represented by this object.


## -syntax


````
void Write();
````


## -parameters






## -returns



This method does not return a value.




## -remarks



This method can be used to reset the region of memory on the target to the currently cached value that was previously read from the target.

It is also possible to directly set the value cached by the <a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a> object, for example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>ExtRemoteData ext_remote_data = new ExtRemoteData(address, sizeof(USHORT));
ext_remote_data.m_Data = (ULONG64) my_ushort;
ext_remote_data.Write();</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544083">ExtRemoteData::Read</a>



<a href="..\engextcpp\nl-engextcpp-extremotedata.md">ExtRemoteData</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [debugger\debugger]:%20ExtRemoteData.Write method%20 RELEASE:%20(2/22/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

