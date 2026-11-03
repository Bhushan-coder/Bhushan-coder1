from pathlib import Path
import re

src = Path("/mnt/data/Bhushan_GitHub_Profile_Midnight_Aurora.md")
text = src.read_text(encoding="utf-8")

# A genuinely different visual direction: "NEON FOREST" — obsidian, deep emerald,
# electric lime and warm ivory, with a clean developer-console aesthetic.
text = text.replace(
    "<!-- MIDNIGHT AURORA THEME: deep-plum gradients, neon orchid and aurora mint -->",
    "<!-- NEON FOREST THEME: obsidian black, emerald green, electric lime and warm ivory -->"
)

# Replace all banner/divider gradient palettes.
text = text.replace(
    "0:10002B,45:3C096C,100:00F5D4",
    "0:050B08,45:123524,100:B7F34A"
)
text = text.replace(
    "0:00F5D4,50:3C096C,100:10002B",
    "0:B7F34A,50:14532D,100:050B08"
)
text = text.replace(
    "0:10002B,50:F15BB5,100:10002B",
    "0:050B08,50:4ADE80,100:050B08"
)

# Consistent neon-green text/badge accents.
text = text.replace("color=00F5D4", "color=B7F34A")
text = text.replace("color=F15BB5", "color=4ADE80")
text = text.replace("color=7209B7", "color=16A34A")
text = text.replace("labelColor=10002B", "labelColor=050B08")
text = text.replace("7B2CBF?style=for-the-badge", "16A34A?style=for-the-badge")
text = text.replace("00B4D8?style=for-the-badge", "B7F34A?style=for-the-badge")
text = text.replace("F15BB5?style=for-the-badge", "4ADE80?style=for-the-badge")

# Green-themed GitHub widgets.
text = text.replace("theme=radical", "theme=merko")
text = text.replace("theme=react-dark", "theme=merko")

# Give the profile a matching, distinctive intro tagline.
text = text.replace(
    "Learn.+Build.+Improve.+Repeat.",
    "Code.+Create.+Grow.+Repeat."
)

out = Path("/mnt/data/Bhushan_GitHub_Profile_Neon_Forest.md")
out.write_text(text, encoding="utf-8")
print(f"Created: {out}")
