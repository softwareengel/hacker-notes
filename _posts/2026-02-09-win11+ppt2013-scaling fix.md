

## The Problem 
- ribbons and layout to huge 

![](../_asset/2026-02-09-win11+ppt2013-scaling%20fix-1770628872620.webp)

- compatibility mode is no more available 
## Solution 

![](../_asset/2026-02-09-win11+ppt2013-scaling%20fix-1770628709762.webp)

### Step-by-step: The Registry Method (Manual Override)

This method manually adds a compatibility flag to the Windows registry that mimics the "System (Enhanced)" setting.

1. Press `Win + R`, type **regedit**, and hit Enter.
    
2. Navigate to the following path: `HKEY_CURRENT_USER\Software\Microsoft\Windows NT\CurrentVersion\AppCompatFlags\Layers` _(If the "Layers" key doesn't exist, right-click AppCompatFlags > New > Key and name it Layers)._
    
3. Right-click in the right-hand pane and select **New > String Value**.
    
4. **Name the value:** Type the full path to your PowerPoint executable.
    
    - For Office 2013, it is usually: `C:\Program Files\Microsoft Office\Office15\POWERPNT.EXE`
        
    - _(If you are on a 32-bit install: `C:\Program Files (x86)\Microsoft Office\Office15\POWERPNT.EXE`)_
        
5. Double-click your new entry and set the **Value data** to: `~ DPIUNAWARE` (to stop scaling entirely) or `~ HIGHDPIAWARE`
    
    - **Try this specific string first:** `~ GDISCALING DPIUNAWARE`


## Result 


- fixed scaling 
- working possible ;-) 
![](../_asset/2026-02-09-win11+ppt2013-scaling%20fix-1770629021659.webp)
