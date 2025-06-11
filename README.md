## custom stuff
`tf/custom` stuff i've made! reach out at spiritov_v@pm.me to commission stuff within the scope of this repo\
(i won't reply to questions)

## health image installation
> [!IMPORTANT]
> `resource/ui/HudPlayerHealth.res` and a `scripts/` health animation file need to be replaced for these to work. take a look at the [preinstalled](/health-images/preinstalled/) huds to see what they edit, or read below.

> [!NOTE]
> positions and properties may be different for all huds and image sizes, and additional positioning troubleshooting may be necessary.

move health `.vmt` and `.vtf`s to `materials/vgui/replay/thumbnails/`
![image](https://github.com/user-attachments/assets/069a0605-0abc-45dc-886d-0222aa5ca6b6)


<details>
  <summary>edit health ui</summary>
<br/>
  
update or add these keys in `resource/ui/hudplayerhealth.res` 
```json
"buff"
{
	"ControlName"          "ImagePanel"
	"fieldName"          "buff"
	"xpos"          "95"
	"ypos"          "35"
	"zpos"          "-4"
	"wide"          "150"
	"tall"          "150"
	"visible"          "1"
	"enabled"          "1"
	"image"          "../vgui/replay/thumbnails/healthbuff"
	"scaleImage"          "1"

	"alpha"           "0"
	"pin_to_sibling"                            "HealthAnchor"
	"pin_corner_to_sibling" "0"
	"pin_to_sibling_corner" "0"
}

"hurt"
{
	"ControlName"          "ImagePanel"
	"fieldName"          "hurt"
	"xpos"          "95"
	"ypos"          "35"
	"zpos"          "-4"
	"wide"          "150"
	"tall"          "150"
	"visible"          "1"
	"enabled"          "1"
	"image"          "../vgui/replay/thumbnails/healthhurt"
	"scaleImage"          "1"

	"alpha"           "0"
	"pin_to_sibling"                            "HealthAnchor"
	"pin_corner_to_sibling" "0"
	"pin_to_sibling_corner" "0"
}
```
</details>
<details>
  <summary>edit hud animations</summary>
<br/>
  
update or add these events in `scripts/"healthanimationfile".txt`
```js
event HudHealthBonusPulse
{
 	RunEvent HudHealthBonusPulseLoop	0.8
 	Animate buff	Alpha "255" Linear 	0.0 0.3
	Animate	buff	Alpha "150" Accel 	0.3 0.4
}

event HudHealthBonusPulseLoop
{
	RunEvent HudHealthBonusPulse	0.0
}

event HudHealthBonusPulseStop
{
	StopEvent HudHealthBonusPulse	0.0
	StopEvent HudHealthBonusPulseLoop	0.0
	Animate	buff	Alpha "0" Linear 0.0 0.0
}

event HudHealthDyingPulse
{
	RunEvent HudHealthDyingPulseLoop	0.4
	Animate	hurt	Alpha "255" Linear 0.0 0.15
	Animate	hurt	Alpha "100" Linear 0.15 0.2
	Animate	buff	Alpha "0" Linear 0.0 0.0
}

event HudHealthDyingPulseLoop
{
	RunEvent HudHealthDyingPulse	0.0
}

event HudHealthDyingPulseStop
{
	StopEvent HudHealthDyingPulse	0.0
	StopEvent HudHealthDyingPulseLoop	0.0
	Animate	buff	Alpha "0" Linear 0.0 0.0
	Animate	hurt	Alpha "0" Linear 0.0 0.0
}
```
</details>

## images
> #### [ascii faces](/health-images/preinstalled/ascii-faces/)
> buff
>
> ![image](https://github.com/user-attachments/assets/b8933603-7d52-41d1-a924-afb55f3eecd3)
> 
> hurt
> 
> ![image](https://github.com/user-attachments/assets/832cb75d-d0b6-445d-b4de-a6f3f1d9d82b)

> #### [oyasumi](/health-images/preinstalled/oyasumi/) [(image source)](https://www.pixiv.net/artworks/75496673)
> buff
> ![image](https://github.com/user-attachments/assets/cbf06c3f-fe69-4aed-b2b5-1e235befa3ab)
> hurt
> ![image](https://github.com/user-attachments/assets/523278f6-5fa4-42f6-8615-eb3dcd0e641b)
> halo
> ![image](https://github.com/user-attachments/assets/ded576cf-1a81-4b7e-91cf-172bcdc2693a)

> #### purple rockettrail
> ![image](https://github.com/user-attachments/assets/85cce5e0-d525-4164-a270-58f2426be587)
