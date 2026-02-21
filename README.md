# score-cat-photo-composition

Scores the composition and visual clarity of a cat photograph from 0 to 1. Evaluates subject clarity, intentional framing, and light and environment — prioritizing visual intention over technical perfection.

## How It Works

`score-cat-photo-composition` receives a single cat photograph and produces a scalar score between **0** (poor composition) and **1** (excellent composition). The score reflects how well the image works as a composed photograph with the cat as its undeniable subject.

The function does not chase technical perfection. It does not reward megapixels, color accuracy, or the prestige of the camera. A slightly grainy phone photo with strong natural composition should outscore a high-resolution studio image where the cat is lost in clutter. What matters is whether the photograph communicates its subject clearly, naturally, and with a sense of visual intention.

## Input

| Field | Type | Description |
|-------|------|-------------|
| input | `image` | A picture of a cat to evaluate for composition and visual clarity. |

The function accepts a single cat photograph from any source — phone camera, professional shoot, social media upload, or security camera still. No metadata, context, or story is required. The function evaluates only what the image presents to the viewer.

## Output

A scalar number between **0** and **1**:

- **0.0 – 0.2**: Poor composition. The cat is difficult to find, out of focus, badly framed, or overwhelmed by its environment.
- **0.2 – 0.4**: Weak composition. The cat is present but does not command the image. Significant issues with clarity, framing, or environment.
- **0.4 – 0.6**: Moderate composition. The cat is visible and identifiable, but the photograph lacks visual intention or has notable distractions.
- **0.6 – 0.8**: Strong composition. The cat is clear, well-framed, and supported by its environment. The photograph feels deliberate.
- **0.8 – 1.0**: Excellent composition. The cat commands the image with clarity, the framing feels purposeful, and the light and environment create harmony around the subject.

## What It Evaluates

The function evaluates three core qualities. Each is handled by a dedicated sub-function, and their weighted outputs combine to produce the final score.

### 1. Subject Clarity — [{{ .Task0 }}](https://github.com/{{ .Owner }}/{{ .Task0 }})

The most fundamental evaluation: can you see the cat? This sub-function scores whether the cat is in focus, visually distinct from its surroundings, and immediately recognizable as the center of the image at first glance.

It considers:
- Whether the cat is in focus and sharply rendered relative to the rest of the image
- Whether the cat is large enough in the frame to register as the subject
- Whether the cat contrasts sufficiently against its surroundings rather than blending in
- Whether competing visual elements pull the viewer's eye away from the cat
- Whether the cat is the first thing a viewer notices at a glance

A photograph with strong subject clarity makes the cat plainly, unmistakably present. The cat commands the image without requiring the viewer to search, squint, or zoom in.

### 2. Intentional Framing — [{{ .Task1 }}](https://github.com/{{ .Owner }}/{{ .Task1 }})

This sub-function scores how deliberate and effective the composition feels — whether the spatial arrangement of elements serves the cat as the focal point.

It considers:
- Whether the cat is positioned purposefully within the frame, not awkwardly cropped or lost in empty space
- Whether leading lines, natural boundaries, or environmental geometry guide the eye toward the cat
- Whether the overall arrangement feels balanced and purposeful
- Whether there is a sense of visual order that works in the cat's favor
- Whether the photograph feels like a portrait of a cat, not merely an image that happens to contain one

Strong framing is not about rigid compositional rules. A cat centered in a simple frame and a cat caught along a dynamic diagonal can both score beautifully. What matters is that the framing feels like it was made for this cat in this moment.

### 3. Light and Environment — [{{ .Task2 }}](https://github.com/{{ .Owner }}/{{ .Task2 }})

This sub-function scores how well the lighting reveals the cat and how effectively the background supports the subject rather than competing with it.

It considers:
- Whether the lighting reveals the cat's features, texture, and form without harsh overexposure or deep shadow
- Whether the light feels natural and serves the subject rather than creating distracting artifacts
- Whether the background is clean and non-distracting or cluttered and chaotic
- Whether the overall visual setting creates harmony around the cat

A humble kitchen with soft window light can score beautifully. A pristine garden with confusing dappled shadows across the cat's face can score poorly. What matters is whether light and setting work together to let the cat be seen and appreciated.

## Use Cases

- **Social media curation**: Surface the most visually compelling cat photos in a feed, elevating strong compositions over blurry or chaotic snapshots.
- **Pet adoption platforms**: Help shelters select the most effective photograph for each animal's profile — well-composed images draw more attention and more adoptions.
- **Photography education**: Provide gentle, structured feedback helping photographers understand what makes one cat photo more visually effective than another.
- **Content moderation**: Filter out extremely low-quality images that fail basic composition standards before they reach users.
- **Automated selection**: Choose the best photograph from a batch of cat images for use in marketing, editorial, or display contexts.

## Philosophy

This function encodes a clear point of view: **clarity matters more than resolution, intention matters more than equipment, and the subject should always be the star.** The score reflects the human experience of looking at a photograph and feeling that it simply works — the cat is there, it is beautiful, and nothing gets in the way of appreciating it.
