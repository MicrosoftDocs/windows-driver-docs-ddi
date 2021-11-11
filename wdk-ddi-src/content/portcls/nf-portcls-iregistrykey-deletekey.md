---
UID: NF:portcls.IRegistryKey.DeleteKey
title: IRegistryKey::DeleteKey (portcls.h)
description: The DeleteKey method deletes the registry key.
old-location: audio\iregistrykey_deletekey.htm
tech.root: audio
ms.date: 05/08/2018
keywords: ["IRegistryKey::DeleteKey"]
ms.keywords: DeleteKey, DeleteKey method [Audio Devices], DeleteKey method [Audio Devices],IRegistryKey interface, IRegistryKey interface [Audio Devices],DeleteKey method, IRegistryKey.DeleteKey, IRegistryKey::DeleteKey, audio.iregistrykey_deletekey, audmp-routines_b5556b44-0bf4-47d2-8bbd-65d12c393341.xml, portcls/IRegistryKey::DeleteKey
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
targetos: Windows
req.typenames: 
f1_keywords:
 - IRegistryKey::DeleteKey
 - portcls/IRegistryKey::DeleteKey
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - portcls.h
api_name:
 - IRegistryKey::DeleteKey
---

# IRegistryKey::DeleteKey


## -description

The <code>DeleteKey</code> method deletes the registry key.

## -returns

<code>DeleteKey</code> returns STATUS_SUCCESS if the call was successful. Otherwise, the method returns an appropriate error code.

## -remarks

A caller deletes an <b>IRegistryKey</b> object's registry key by calling the <code>DeleteKey</code> method on that object. The key can be deleted only if the caller created the key with an <a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a> that permits deletion. The caller enables deletion by specifying a <i>DesiredAccess</i> parameter value of KEY_ALL_ACCESS (described in <a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>) to the <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewregistrykey">PcNewRegistryKey</a>, <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-newregistrykey">IPort::NewRegistryKey</a>, or <a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-newsubkey">IRegistryKey::NewSubKey</a> call that creates the key. When deleting a key, the <b>IRegistryKey</b> object discards its registry-key handle, and all other handles to the deleted key become invalid.

## -see-also

<a href="/windows-hardware/drivers/kernel/access-mask">ACCESS_MASK</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iport-newregistrykey">IPort::NewRegistryKey</a>



<a href="/windows-hardware/drivers/ddi/portcls/nn-portcls-iregistrykey">IRegistryKey</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-iregistrykey-newsubkey">IRegistryKey::NewSubKey</a>



<a href="/windows-hardware/drivers/ddi/portcls/nf-portcls-pcnewregistrykey">PcNewRegistryKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwcreatekey">ZwCreateKey</a>



<a href="/windows-hardware/drivers/ddi/wdm/nf-wdm-zwdeletekey">ZwDeleteKey</a>

