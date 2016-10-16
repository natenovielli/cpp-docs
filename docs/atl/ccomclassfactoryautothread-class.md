---
title: "CComClassFactoryAutoThread Class"
ms.custom: na
ms.date: "10/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CComClassFactoryAutoThread"
  - "ATL.CComClassFactoryAutoThread"
  - "CComClassFactoryAutoThread"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComClassFactoryAutoThread class"
ms.assetid: 22008042-533f-4dd9-bf7e-191ee571f9a1
caps.latest.revision: 16
ms.author: "mblome"
manager: "ghogen"
translation.priority.ht: 
  - "cs-cz"
  - "de-de"
  - "es-es"
  - "fr-fr"
  - "it-it"
  - "ja-jp"
  - "ko-kr"
  - "pl-pl"
  - "pt-br"
  - "ru-ru"
  - "tr-tr"
  - "zh-cn"
  - "zh-tw"
---
# CComClassFactoryAutoThread Class
This class implements the [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364) interface, and allows objects to be created in multiple apartments.  
  
> [!IMPORTANT]
>  This class and its members cannot be used in applications that execute in the Windows Runtime.  
  
## Syntax  
  
```
class CComClassFactoryAutoThread : public IClassFactory,   public CComObjectRootEx<CComGlobalsThreadModel>
```  
  
## Members  
  
### Public Methods  
  
|Name|Description|  
|----------|-----------------|  
|[CComClassFactoryAutoThread::CreateInstance](../Topic/CComClassFactoryAutoThread::CreateInstance.md)|Creates an object of the specified CLSID.|  
|[CComClassFactoryAutoThread::LockServer](../Topic/CComClassFactoryAutoThread::LockServer.md)|Locks the class factory in memory.|  
  
## Remarks  
 `CComClassFactoryAutoThread` is similar to [CComClassFactory](../atl/ccomclassfactory-class.md), but allows objects to be created in multiple apartments. To take advantage of this support, derive your EXE module from [CComAutoThreadModule](../atl/ccomautothreadmodule-class.md).  
  
 ATL objects normally acquire a class factory by deriving from [CComCoClass](../atl/ccomcoclass-class.md). This class includes the macro [DECLARE_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md), which declares [CComClassFactory](../atl/ccomclassfactory-class.md) as the default class factory. To use `CComClassFactoryAutoThread`, specify the [DECLARE_CLASSFACTORY_AUTO_THREAD](../Topic/DECLARE_CLASSFACTORY_AUTO_THREAD.md) macro in your object's class definition. For example:  
  
 [!code[NVC_ATL_COM#9](../atl/codesnippet/CPP/ccomclassfactoryautothread-class_1.h)]  
  
## Inheritance Hierarchy  
 `CComObjectRootBase`  
  
 [CComObjectRootEx](../atl/ccomobjectrootex-class.md)  
  
 `IClassFactory`  
  
 `CComClassFactoryAutoThread`  
  
## Requirements  
 **Header:** atlcom.h  
  
##  <a name="ccomclassfactoryautothread__createinstance"></a>  CComClassFactoryAutoThread::CreateInstance  
 Creates an object of the specified CLSID and retrieves an interface pointer to this object.  
  
```
STDMETHODIMP CreateInstance(LPUNKNOWN pUnkOuter,
    REFIID riid,
    void**  ppvObj);
```  
  
### Parameters  
 `pUnkOuter`  
 [in] If the object is being created as part of an aggregate, then `pUnkOuter` must be the outer unknown. Otherwise, `pUnkOuter` must be **NULL**.  
  
 `riid`  
 [in] The IID of the requested interface. If `pUnkOuter` is non- **NULL**, `riid` must be **IID_IUnknown**.  
  
 `ppvObj`  
 [out] A pointer to the interface pointer identified by `riid`. If the object does not support this interface, `ppvObj` is set to **NULL**.  
  
### Return Value  
 A standard `HRESULT` value.  
  
### Remarks  
 If your module derives from [CComAutoThreadModule](../atl/ccomautothreadmodule-class.md), `CreateInstance` first selects a thread to create the object in the associated apartment.  
  
##  <a name="ccomclassfactoryautothread__lockserver"></a>  CComClassFactoryAutoThread::LockServer  
 Increments and decrements the module lock count by calling **_Module::Lock** and **_Module::Unlock**, respectively.  
  
```
STDMETHODIMP LockServer(BOOL fLock);
```  
  
### Parameters  
 `fLock`  
 [in] If **TRUE**, the lock count is incremented; otherwise, the lock count is decremented.  
  
### Return Value  
 A standard `HRESULT` value.  
  
### Remarks  
 When using `CComClassFactoryAutoThread`, **_Module** typically refers to the global instance of [CComAutoThreadModule](../atl/ccomautothreadmodule-class.md).  
  
 Calling `LockServer` allows a client to hold onto a class factory so that multiple objects can be quickly created.  
  
## See Also  
 [IClassFactory](http://msdn.microsoft.com/library/windows/desktop/ms694364)   
 [CComClassFactory2 Class](../atl/ccomclassfactory2-class.md)   
 [CComClassFactorySingleton Class](../atl/ccomclassfactorysingleton-class.md)   
 [CComObjectRootEx Class](../atl/ccomobjectrootex-class.md)   
 [CComGlobalsThreadModel](../Topic/CComGlobalsThreadModel.md)   
 [Class Overview](../atl/atl-class-overview.md)
