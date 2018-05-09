---
UID: NF:portcls.IRegistryKey.DeleteKey
title: IRegistryKey::DeleteKey
author: windows-driver-content
description: The DeleteKey method deletes the registry key.
old-location: audio\iregistrykey_deletekey.htm
old-project: audio
ms.assetid: 2930b049-7572-4ee5-bef1-fd4485e5f644
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DeleteKey, DeleteKey method [Audio Devices], DeleteKey method [Audio Devices],IRegistryKey interface, IRegistryKey interface [Audio Devices],DeleteKey method, IRegistryKey.DeleteKey, IRegistryKey::DeleteKey, audio.iregistrykey_deletekey, audmp-routines_b5556b44-0bf4-47d2-8bbd-65d12c393341.xml, portcls/IRegistryKey::DeleteKey
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	portcls.h
api_name:
-	IRegistryKey.DeleteKey
product:
- Windows
targetos: Windows
req.typenames: 
---

# IRegistryKey::DeleteKey


## -description


The <code>DeleteKey</code> method deletes the registry key.


## -parameters






#### - None


## -returns



<code>DeleteKey</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.




## -remarks



A caller deletes an <b>IRegistryKey</b> object's registry key by calling the <code>DeleteKey</code> method on that object. The key can be deleted only if the caller created the key with an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> that permits deletion. The caller enables deletion by specifying a <i>DesiredAccess</i> parameter value of KEY_ALL_ACCESS (described in <a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>) to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff537716">PcNewRegistryKey</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff536970">IRegistryKey::NewSubKey</a> call that creates the key. When deleting a key, the <b>IRegistryKey</b> object discards its registry-key handle, and all other handles to the deleted key become invalid.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536945">IPort::NewRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536965">IRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536970">IRegistryKey::NewSubKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff537716">PcNewRegistryKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566425">ZwCreateKey</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566437">ZwDeleteKey</a>
 

 

