# Maya-commandLineRenderOption
A print out of the command line render option, the same result can be achieved executing the following line in terminal
"/path/to/maya/install/folder/bin/Render -h"


```
Usage: /path/to/maya/install/folder/bin/Render [options] filename
       where "filename" is a Maya ASCII or a Maya binary file.

Common options:
  -help              Print help
  -test              Print Mel commands but do not execute them
  -verb              Print Mel commands before they are executed
  -keepMel           Keep the temporary Mel file
  -listRenderers     List all available renderers
  -renderer string   Use this specific renderer
  -r string          Same as -renderer
  -proj string       Use this Maya project to load the file
  -log string        Save output into the given file
  -rendersetuptemplate string Apply a render setup template to your scene before command line rendering.  Only templates exported via File > Export All in the Render Setup editor are supported.  Render setting presets and AOVs are imported from the template.  Render settings and AOVs are reloaded after the template if the -rsp and -rsa flags are used in conjunction with this flag.
  -rst string        Same as -rendersetuptemplate
  -rendersettingspreset string Apply the scene Render Settings from this template file before command line rendering.  This is equivalent to performing File > Import Scene Render Settings in the Render Setup editor, then batch rendering.
  -rsp string        Same as -rendersettingspreset
  -rendersettingsaov string Import the AOVs from this json file before command line rendering.
  -rsa string        Same as -rendersettingsaov

Specific options for renderer "default": Use the renderer stored in the Maya file

General purpose flags:
  -rd path                    Directory in which to store image file
  -of string                  Output image file format. See the Render Settings window to
        find available formats
  -im filename                Image file output name

Frame numbering options
  -s float                    Starting frame for an animation sequence
  -e float                    End frame for an animation sequence
  -b float                    By frame (or step) for an animation sequence
  -skipExistingFrames boolean Skip frames that are already rendered (if true) or force rendering all frames (if false)
  -pad int                    Number of digits in the output image frame file name
        extension
  -rfs int                    Renumber Frame Start: number for the first image when
        renumbering frames
  -rfb int                    Renumber Frame By (or step) used for renumbering frames
  -fnc int                    File Name Convention: any of name, name.ext, ... See the
        Render Settings window to find available options. Use namec and
        namec.ext for Multi Frame Concatenated formats. As a shortcut,
        numbers 1, 2, ... can also be used

Camera options
  -cam name                   Specify which camera to be rendered
  -rgb boolean                Turn RGB output on or off
  -alpha boolean              Turn Alpha output on or off
  -depth boolean              Turn Depth output on or off
  -iip                        Ignore Image Planes. Turn off all image planes before
        rendering

Resolution options
  -x int                      Set X resolution of the final image
  -y int                      Set Y resolution of the final image
  -percentRes float           Renders the image using percent of the resolution
  -ard float                  Device aspect ratio for the rendered image
  -par float                  Pixel aspect ratio for the rendered image

Render Layers and Passes:
  -rl boolean|name(s)         Render each render layer separately. Applicable to both legacy render layers and render setup. When used with render setup, a rs_ prefix is appended to the name of each folder created for each layer.
  -rp boolean|name(s)         Render passes separately. Only applicable to legacy render layers. 'all' will render all passes
  -sel boolean|name(s)        Selects which objects, groups and/or sets to render

Mel callbacks
  -preRender string           Mel code executed before rendering
  -postRender string          Mel code executed after rendering
  -preLayer string            Mel code executed before each render layer
  -postLayer string           Mel code executed after each render layer
  -preFrame string            Mel code executed before each frame
  -postFrame string           Mel code executed after each frame
  -pre string                 Obsolete flag
  -post string                Obsolete flag

Specific options for the layers who use Maya software renderer:

Anti-aliasing quality only for Maya software renderer:
  -sw:eaa int                 The anti-aliasing quality of EAS (Abuffer). One of:
        highest(0), high(1), medium(2), low(3)
  -sw:ss int                  Global number of shading samples per surface in a pixel
  -sw:mss int                 Maximum number of adaptive shading samples per surface
        in a pixel
  -sw:mvs int                 Number of motion blur visibility samples
  -sw:mvm int                 Maximum number of motion blur visibility samples
  -sw:pss int                 Number of particle visibility samples
  -sw:vs int                  Global number of volume shading samples
  -sw:ufil boolean            If true, use the multi-pixel filtering; otherwise use
        single pixel filtering
  -sw:pft int                 When useFilter is true, identifies one of the following
        filters: box(0), triangle(2), gaussian(4), quadratic(5)
  -sw:pfx float               When useFilter is true, defines the X size of the filter
  -sw:pfy float               When useFilter is true, defines the Y size of the filter
  -sw:rct float               Red channel contrast threshold
  -sw:gct float               Green channel contrast threshold
  -sw:bct float               Blue channel contrast threshold
  -sw:cct float               Pixel coverage contrast threshold (default is 1.0/8.0)

Raytracing quality only for Maya software renderer:
  -sw:ert boolean             Enable ray tracing
  -sw:rfl int                 Maximum ray-tracing reflection level
  -sw:rfr int                 Maximum ray-tracing refraction level
  -sw:sl int                  Maximum ray-tracing shadow ray depth

Field Options only for Maya software renderer:
  -sw:field boolean           Enable field rendering. When on, images are interlaced
  -sw:pal                     When field rendering is enabled, render even field
        first (PAL)
  -sw:ntsc                    When field rendering is enabled, render odd field
        first (NTSC)

Motion Blur only for Maya software renderer:
  -sw:mb boolean              Motion blur on/off
  -sw:mbf float               Motion blur by frame
  -sw:sa float                Shutter angle for motion blur (1-360)
  -sw:mb2d boolean            Motion blur 2D on/off
  -sw:bll float               2D motion blur blur length
  -sw:bls float               2D motion blur blur sharpness
  -sw:smv int                 2D motion blur smooth value
  -sw:smc boolean             2D motion blur smooth color on/off
  -sw:kmv boolean             Keep motion vector for 2D motion blur on/off

Render Options only for Maya software renderer:
  -sw:ifg boolean             Use the film gate for rendering if false
  -sw:edm boolean             Enable depth map usage
  -sw:g float                 Gamma value
  -sw:premul boolean          Premultiply color by the alpha value
  -sw:premulthr float         When premultiply is on, defines the threshold used to
        determine whether to premultiply or not

Memory and Performance only for Maya software renderer:
  -sw:uf boolean              Use the tessellation file cache
  -sw:oi boolean              Dynamically detects similarly tessellated surfaces
  -sw:rut boolean             Reuse render geometry to generate depth maps
  -sw:udb boolean             Use the displacement bounding box scale to optimize
        displacement-map performance
  -sw:mm int                  Renderer maximum memory use (in Megabytes)

Specific options for the layers who use Maya hardware renderer:

Quality flags only for Maya hardware renderer:
  -hw:ehl boolean             Enable high quality lighting
  -hw:ams boolean             Accelerated multi sampling
  -hw:ns int                  Number of samples per pixel
  -hw:tsc boolean             Transparent shadow maps
  -hw:ctr int                 Color texture resolution
  -hw:btr int                 Bump texture resolution
  -hw:tc boolean              Enable texture compression

Render options only for Maya hardware renderer:
  -hw:c boolean               Culling mode.
                0: per object.
                1: all double sided.
                2: all single sided
  -hw:sco boolean             Enable small object culling
  -hw:ct float                Small object culling threshold

Render options only for Maya hardware 2.0 renderer:

Mel callbacks only for Maya hardware renderer:
  -hw:mb boolean              Enable motion blur
  -hw:mbf float               Motion blur by frame
  -hw:ne int                  Number of exposures
  -hw:egm boolean             Enable geometry mask

 *** Remember to place a space between option flags and their arguments. ***
Any boolean flag will take the following values as TRUE: on, yes, true, or 1.
Any boolean flag will take the following values as FALSE: off, no, false, or 0.

    e.g. -s 1 -e 10 -x 512 -y 512 -cam persp -mr:v 5 file.

```
