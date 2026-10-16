# Murmation

An interactive single-page website that simulates a flock of starlings against a dusk sky. Move your cursor (or finger) and the flock follows. Three sliders change the rules each bird follows, so you can watch the flock tighten, spread out, or fall apart in real time.

No build step, no dependencies, no framework. It is one HTML file.

Run it

Download or clone the repo, then open murmuration.html in any modern browser.

bash
git clone <your-repo-url>
cd <your-repo-folder>
open murmuration.html   # macOS; on Windows use: start murmuration.html
Host it for free with GitHub Pages
Rename murmuration.html to index.html.
In your repo, go to Settings → Pages.
Under Build and deployment, choose Deploy from a branch, select main and / (root), then save.
After a minute or so, your site will be live at the URL GitHub shows on that page.
How it works

The flock uses the classic "boids" model. Each bird looks at nearby neighbours and applies three rules:

Keep space: steer away from birds that are too close.
Match direction: adjust heading toward the average heading of neighbours.
Stay close: drift toward the centre of nearby birds.

None of the birds has a leader or a plan. The flock-wide movement comes entirely from these local rules. The sliders scale how strongly each rule pulls.

Birds are drawn on a full-screen <canvas>, and the page content scrolls over it.

Customise
What	Where
Colours	The :root block at the top of the <style> section
Fonts	The Google Fonts <link> and the --display / --body variables
Starting flock size and maximum	START and MAX in the script
Starting slider values	The value attributes on the three range inputs
Bird speed	MINV and MAXV in the script
How far birds sense neighbours	R in the script
Cursor attraction	The mouse block inside step()
Accessibility
Respects prefers-reduced-motion: if enabled, the flock is drawn as a still image instead of animating.
Sliders and buttons have visible keyboard focus.
Layout is responsive down to phone widths.
Notes
Performance depends on flock size. Each bird checks its neighbours every frame, so very large flocks may slow down on older devices. Lower MAX if needed.
Fonts load from Google Fonts. Offline, the page falls back to system fonts.
