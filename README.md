# Lasers

The sun acts as a massive source of ambient direct current light that easily saturates the receiver or creates too much noise for the robot to distinguish the laser beam. 

### What should the wavelenth of the laser be for it to be visible?
Since the competetion is outdoors, therefore we need a laser with wavelegth visible to the human eye & in sunlight.
--> visible light ranges between **380 nm** & **750 nm**.

![image alt](https://github.com/maiwagdy/Laser/blob/9c808426c84b25f0d771dd09317f865f53866031/the-visible-light-spectrum-2699036_FINAL2-c0b0ee6f82764efdb62a1af9b9525050.png)

- Sunlight makes detection even harder because:
The bright background reduces your eyes' sensitivity.
Any very faint glow near the edge of the visible spectrum (around 700–780 nm) can be washed out by sunlight.
IR lasers operate at wavelengths longer than **700 nm**, so the beam itself is usually invisible.

### The effect of sunlight on laser visibilty : 
Sunlight severely reduces laser visibility because ambient sunlight overpowers & washes out the focused, coherent light of the laser beam. While indoor environments typically have **100** to **500** lux, direct sunlight can reach **10,000** to **100,000** lux.

#### Why sunlight blinds light? 
**1. sensor saturation:** Sunlight delivers up to 1,000 watts of optical power per square meter. This intense energy can completely flood your sensor, causing it to output its maximum voltage continuously and making it blind to the laser's added light.

**2. Direct current (DC) offset:** Sunlight creates a massive, steady background electrical signal in your sensor. Your laser signal sits on top of this giant baseline, making the tiny fluctuations from the laser incredibly difficult for your circuit to read.

**3. Shot noise:** The random arrival of photons from the sun creates electrical "hiss" or noise in the detector. This noise can easily be much stronger than your actual laser signal, entirely burying it.

- Wavelength Competition: 
Sunlight contains a broad spectrum of all visible light frequencies. Because the sun floods the visual spectrum, your eyes cannot isolate the specific wavelength of a laser (such as red or green).
- Colour Differences: 
The human eye is much more sensitive to the green spectrum (around 532 nm) compared to red. Because it sits closer to the center of our visible color spectrum, a green laser will appear up to 50 times brighter than a red laser of the same strength in daylight.

## Types of lasers visible in sunlight

### 1. Green Laser Diodes 
- Wavelength: 520 nm - 532 nm 
- Key Advantage: They are up to four times more visible in direct, bright sunlight than red lasers, significantly reducing measurement error and manual aiming guesswork.

- When you apply an electric current to the diode, electrons drop across a specific atomic energy gap (the material's "bandgap") inside the **InGaN active layer**.Because InGaN is a direct bandgap material, this drop converts the electrical energy directly into a stream of green photons.The sides of the tiny semiconductor chip are polished to act as internal mirrors. This causes the green photons to bounce back and forth, amplifying until a coherent green laser beam shoots out of the front edge.

- The InGaN (Indium Gallium Nitride) active layer in laser diodes is the core region where electrical energy is converted into coherent laser light. It operates by capturing injected electrons and holes, which recombine to emit intense light through stimulated emission.

[Positive Voltage In]  ───> ┌─────────────────────────┐
                            │  p-Type Semiconductor   │
                            ├─────────────────────────┤
   [Direct Photon Energy] ──>  Active InGaN Green Layer ───> [ 520nm GREEN BEAM ]
                            ├─────────────────────────┤
[Negative Voltage In]  ───> │  n-Type Semiconductor   │
                            └─────────────────────────┘
                    

### Why they're ideal for sunlight & robotics :
  Direct green lasers eliminate the physics constraints of 
  older tech; 
  **Massive Temperature Window:** Because they do not rely on fragile, temperature-sensitive crystals, direct diodes operate from -20°C to +60°C & up to 85°C on advanced units. A robot can go from a freezing warehouse to hot direct sunlight without the laser dropping power or shifting wavelengths.
  **Ultra-Fast Electronic Modulation:** You can turn a direct diode on & off billions of times per second (megahertz speeds).
  **Physical Ruggedness:** The laser is a solid-state piece of silicon & metal inside a sealed metal can. It has no delicate mirrors or floating crystals to knock out of alignment, allowing it to withstand high shock, vibration, & drops on robotic rovers.


## DPSS or DDL 

#### DPSS (diode pumped solid state) 

Green (532 nm): The most common DPSS laser, used in laser pointers, light shows, and alignment tools.

Disadvantages: The extra steps required to convert the light generate waste heat and make the system less energy-efficient and more temperature-sensitive.

#### DDL (direct diode laser)
Direct Conversion: Electrical energy is converted directly into coherent light within a semiconductor diode.

No Intermediate Medium: Unlike Diode-Pumped Solid-State (DPSS) lasers or fiber lasers, DDLs do not require an intermediate gain medium (such as a crystal or optical fiber) to amplify or convert the wavelength.

Wavelengths: Standard DDLs operate in the near-infrared range (typically 800–1000 nm), while visible blue DDLs (around 450 nm) use different materials to process highly reflective metals.

Disadvantages : Lower Beam Quality.

### DDL & DPSS 
Direct Diode Lasers (DDL) and Diode-Pumped Solid-State (DPSS) lasers differ fundamentally in how they generate light,
with DDL offering superior electrical efficiency and lower cost, while DPSS delivers exceptional beam quality and precise visible/UV wavelengths.

The core difference is that a DDL shines its laser light directly from a semiconductor diode onto the target, whereas a DPSS uses a laser diode only as an energy source to "pump" a crystal, which then generates a much more refined laser beam.

## Relation between the wavelength & the distance

- **distance** & **wavelength** aren't directly proportional, as for laser spot the main factors are :

### 1. Brightness perceived by the eye :

Different wavelengths are seen differently by the human eye.

- Green (~520–532 nm) is highly visible.
- Red (~650 nm) appears dimmer at the same power.
- Infrared is invisible.

### 2. Beam divergence

As a laser travels, the beam spreads out. The fundamental diffraction relationship is:

- θ = D / λ

where;

θ = beam divergence angle
λ = wavelength
D = beam diameter at the aperture
This means:
- Longer wavelengths diverge slightly more.
- Shorter wavelengths diverge slightly less.


## Comparision between 520nm & 532nm green lasers 

Both 520 nm and 532 nm lasers are commonly used where high visibility is required. For a UGVC robot that must indicate successful person detection outdoors, the choice depends on visibility, reliability, power consumption, and environmental performance.

### 1. Wavelength and colour
**520 nm**, visibility to human eye is high
**532 nm**, visibility to human eye is high (closer to peak eye sensitivity).

The human eye is most sensitive around 555 nm, so 532 nm is slightly closer to this peak.

### 2. Perceived brightness

**520 nm**	high
**532 nm**   slightly higher

### 3. Technology

#### 520 nm lasers are direct-diode lasers.

##### Advantages:

- Simpler design
- Fewer internal optical components
- More robust construction
- Higher reliability

#### 532 nm lasers are DPSS (Diode-Pumped Solid-State) lasers.

##### Advantages:

- capable of producing very bright green beams

#### Disadvantages:

- More complex optical system
- More components that can drift or fail
- Performance may vary with temperature

### 4. temperature performance
**520nm** has better performance and durabilty under different weather conditions.

### 5. Power consumtion 
**520nm** is more effient and requires lower power input than **532nm**

## Conclusion

Both **520** nm and **532 nm** lasers can satisfy the UGVC requirement. However, for an outdoor autonomous robot operating, 520 nm is the recommended choice.

#### Reasons:

- 1. More reliable 
- 2. Better performance across changing temperatures.
- 3. Lower power consumption.
- 4. instant startup.
- 5. Nearly identical practical visibility at the required distance.
- 6. The small brightness advantage of **532 nm** does not outweigh the operational advantages of **520 nm** for this application.
