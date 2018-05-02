---
UID: NF:sensorsclassextension.ISensorClassExtension.PostStateChange
title: ISensorClassExtension::PostStateChange
author: windows-driver-content
description: The ISensorClassExtension::PostStateChange method notifies the sensor class extension about a change in the operational state of the sensor.
old-location: sensors\isensorclassextension_poststatechange.htm
old-project: sensors
ms.assetid: ae3bc846-df63-4186-9554-f4600e1f2066
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: ISensorClassExtension interface [Sensor Devices],PostStateChange method, ISensorClassExtension.PostStateChange, ISensorClassExtension::PostStateChange, PostStateChange, PostStateChange method [Sensor Devices], PostStateChange method [Sensor Devices],ISensorClassExtension interface, Sensor_IFaces_b6cc2565-ed4f-48cb-83ea-8d03322c2670.xml, sensors.isensorclassextension_poststatechange, sensorsclassextension/ISensorClassExtension::PostStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: sensorsclassextension.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Windows 7,Available in Windows 7.
req.target-min-winversvr: None supported
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: SensorsClassExtension.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	SensorsClassExtension.lib
-	SensorsClassExtension.dll
api_name:
-	ISensorClassExtension.PostStateChange
product:
- Windows
targetos: Windows
req.typenames: 
---

# ISensorClassExtension::PostStateChange


## -description


The <b>ISensorClassExtension::PostStateChange</b> method notifies the sensor class extension about a change in the operational state of the sensor.


## -parameters




### -param pwszSensorID [in]

<b>LPWSTR</b> that contains the ID for the sensor for which the driver is raising the event.


### -param state






#### - State [in]


<a href="https://msdn.microsoft.com/library/windows/hardware/ff545708">SensorState</a> value that indicates the new state.


## -returns



This method returns an HRESULT. Possible values include, but are not limited to, one of the following values.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The method succeeded.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_POINTER</b></dt>
</dl>
</td>
<td width="60%">
A required pointer argument was <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>HRESULT_FROM_WIN32(ERROR_CAN_NOT_COMPLETE)</b></dt>
</dl>
</td>
<td width="60%">
The class extension is not initialized.

</td>
</tr>
</table>
 




## -remarks



Sensor state information is also available through the <a href="https://msdn.microsoft.com/1BF1568D-A889-4158-9C6D-160D9B06F0DE">SENSOR_PROPERTY_STATE</a> property key.

<div class="code"></div>

#### Examples

The following example code demonstrates a function that posts a state-changed event.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>HRESULT PostStateEvent()
{
    // Validate that we have a pointer to the class extension.
    HRESULT hr = (NULL == m_spSensorCXT) ? E_UNEXPECTED : S_OK ;

    if (SUCCEEDED(hr))
    {
        SensorState st;

        // Retrieve the sensor state
        hr = m_pDdi-&gt;GetSensorState(&amp;st);

        if (SUCCEEDED(hr))
        {
            // Post the state change event.
            hr = m_spSensorCXT-&gt;PostStateChange(g_wszSensorID, st);
        }
    }

    return hr;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545503">ISensorClassExtension</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545589">ISensorDriver::OnClientSubscribeToEvents</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545598">ISensorDriver::OnClientUnsubscribeFromEvents</a>
 

 

