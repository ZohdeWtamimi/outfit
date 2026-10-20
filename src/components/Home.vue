<template>
    <div class="bg-white min-h-screen overflow-hidden" dir="rtl" lang="ar">
        <div class="hb">
            <header class="top">
                <div style="display: flex; align-items: center; gap: 10px; gap: 10px;justify-content: center; margin-top: 10px;">
                    <h1 style="color: black;">Outfit</h1>
                    <img :src="oImg" style="border-radius: 10px;"  width="40" height="40" alt="Outfit" />
                </div>
            </header>

            <div class="app">
                <!-- Preview -->
                <section class="stage" aria-label="معاينة الهودي">
                    <div class="stage-top">
                        <span class="colorname">{{ currentColor.name }}</span>
                        <div class="seg" role="group" aria-label="العرض">
                            <button type="button" :aria-pressed="view === 'front'" @click="view = 'front'">الواجهة</button>
                            <button type="button" :aria-pressed="view === 'back'" @click="view = 'back'">الخلفية</button>
                        </div>
                    </div>

                    <svg
                        ref="svgEl"
                        class="hoodie"
                        viewBox="0 0 400 460"
                        role="group"
                        :aria-label="`${currentColor.name} هودي، عرض ${view}`"
                        :style="{ '--hood': currentColor.hex }"
                    >
                        <defs>
                            <path id="hb-sil" d="M152,58 Q120,66 100,84 C78,104 52,250 34,372 L36,392 Q60,402 86,398 C92,340 108,260 118,206 C116,280 114,360 116,424 Q200,436 284,424 C286,360 284,280 282,206 C292,260 308,340 314,398 Q340,402 364,392 L366,372 C348,250 322,104 300,84 Q280,66 248,58 Z" />
                            <path id="hb-hoodF" d="M140,68 C130,28 160,8 200,8 C240,8 270,28 260,68 C256,100 232,126 200,130 C168,126 144,100 140,68 Z" />
                            <path id="hb-hoodOpen" d="M152,64 C150,38 172,26 200,26 C228,26 250,38 248,64 C246,90 226,112 200,116 C174,112 154,90 152,64 Z" />
                            <path id="hb-hoodB" d="M140,68 C130,28 160,8 200,8 C240,8 270,28 260,68 C262,104 236,142 200,144 C164,142 138,104 140,68 Z" />
                            <path id="hb-cL" d="M36,364 Q62,374 90,368 L86,397 Q60,401 37,391 Z" />
                            <path id="hb-cR" d="M364,364 Q338,374 310,368 L314,397 Q340,401 363,391 Z" />
                            <path id="hb-hm" d="M116,402 Q200,414 284,402 L284,424 Q200,436 116,424 Z" />
                            <pattern id="hb-rib" width="4.5" height="10" patternUnits="userSpaceOnUse">
                                <rect width="4.5" height="10" fill="rgba(0,0,0,.07)" />
                                <rect width="1.6" height="10" fill="rgba(0,0,0,.22)" />
                            </pattern>
                            <linearGradient id="hb-shade" x1="0" x2="1" y1="0" y2="0">
                                <stop offset="0" stop-color="#000" stop-opacity=".30" />
                                <stop offset=".2" stop-color="#000" stop-opacity=".07" />
                                <stop offset=".5" stop-color="#fff" stop-opacity=".08" />
                                <stop offset=".8" stop-color="#000" stop-opacity=".07" />
                                <stop offset="1" stop-color="#000" stop-opacity=".30" />
                            </linearGradient>
                            <radialGradient id="hb-floor">
                                <stop offset="0" stop-color="#000" stop-opacity=".30" />
                                <stop offset="1" stop-color="#000" stop-opacity="0" />
                            </radialGradient>
                            <g id="hb-ribs" stroke="rgba(0,0,0,.3)" stroke-width="1" stroke-linejoin="round">
                                <use href="#hb-cL" class="fabric" />
                                <use href="#hb-cR" class="fabric" />
                                <use href="#hb-hm" class="fabric" />
                                <use href="#hb-cL" fill="url(#hb-rib)" />
                                <use href="#hb-cR" fill="url(#hb-rib)" />
                                <use href="#hb-hm" fill="url(#hb-rib)" />
                            </g>
                        </defs>

                        <ellipse cx="200" cy="443" rx="150" ry="11" fill="url(#hb-floor)" />

                        <!-- FRONT -->
                        <g v-show="view === 'front'">
                            <use href="#hb-sil" class="fabric" stroke="rgba(0,0,0,.38)" stroke-width="1.2" stroke-linejoin="round" />
                            <g fill="none" stroke-linecap="round">
                                <path d="M104,92 C126,120 120,170 118,206" stroke="rgba(0,0,0,.24)" stroke-width="1.4" />
                                <path d="M296,92 C274,120 280,170 282,206" stroke="rgba(0,0,0,.24)" stroke-width="1.4" />
                                <path d="M120,214 C146,236 158,262 150,288" stroke="rgba(0,0,0,.14)" stroke-width="2.4" />
                                <path d="M280,214 C254,236 242,262 250,288" stroke="rgba(0,0,0,.14)" stroke-width="2.4" />
                                <path d="M70,150 C74,200 66,250 58,300" stroke="rgba(0,0,0,.12)" stroke-width="2.2" />
                                <path d="M330,150 C326,200 334,250 342,300" stroke="rgba(0,0,0,.12)" stroke-width="2.2" />
                                <path d="M84,130 C86,190 80,240 74,290" stroke="rgba(255,255,255,.07)" stroke-width="3" />
                                <path d="M316,130 C314,190 320,240 326,290" stroke="rgba(255,255,255,.07)" stroke-width="3" />
                            </g>
                            <path d="M146,282 Q200,272 254,282 L274,382 Q200,394 126,382 Z" fill="rgba(0,0,0,.07)" stroke="rgba(0,0,0,.3)" stroke-width="1.3" stroke-linejoin="round" />
                            <path d="M148,285 Q200,275 252,285" fill="none" stroke="rgba(255,255,255,.1)" stroke-width="1.5" />
                            <use href="#hb-ribs" />
                            <use href="#hb-hoodF" class="fabric" stroke="rgba(0,0,0,.38)" stroke-width="1.2" stroke-linejoin="round" />
                            <use href="#hb-hoodOpen" fill="#000" fill-opacity=".58" />
                            <use href="#hb-hoodOpen" fill="none" stroke="rgba(0,0,0,.4)" stroke-width="1.5" />

                            <g pointer-events="none">
                                <path d="M184,122 C182,145 181,160 182,184" fill="none" stroke="#DAD6CB" stroke-width="2.8" stroke-linecap="round" />
                                <path d="M216,122 C218,145 219,160 218,184" fill="none" stroke="#DAD6CB" stroke-width="2.8" stroke-linecap="round" />
                                <rect x="179.6" y="182" width="4.8" height="13" rx="2" fill="#2A2C30" />
                                <rect x="215.6" y="182" width="4.8" height="13" rx="2" fill="#2A2C30" />
                                <circle cx="184" cy="122" r="2.6" fill="#2A2C30" />
                                <circle cx="216" cy="122" r="2.6" fill="#2A2C30" />
                            </g>
                            <g pointer-events="none">
                                <use href="#hb-sil" fill="url(#hb-shade)" />
                                <use href="#hb-hoodF" fill="url(#hb-shade)" />
                            </g>
                        </g>

                        <!-- BACK -->
                        <g v-show="view === 'back'">
                            <use href="#hb-sil" class="fabric" stroke="rgba(0,0,0,.38)" stroke-width="1.2" stroke-linejoin="round" />
                            <g fill="none" stroke-linecap="round">
                                <path d="M104,92 C126,120 120,170 118,206" stroke="rgba(0,0,0,.24)" stroke-width="1.4" />
                                <path d="M296,92 C274,120 280,170 282,206" stroke="rgba(0,0,0,.24)" stroke-width="1.4" />
                                <path d="M116,152 Q200,172 284,152" stroke="rgba(0,0,0,.16)" stroke-width="1.3" />
                                <path d="M120,230 C146,252 156,290 150,330" stroke="rgba(0,0,0,.12)" stroke-width="2.4" />
                                <path d="M280,230 C254,252 244,290 250,330" stroke="rgba(0,0,0,.12)" stroke-width="2.4" />
                                <path d="M70,150 C74,200 66,250 58,300" stroke="rgba(0,0,0,.12)" stroke-width="2.2" />
                                <path d="M330,150 C326,200 334,250 342,300" stroke="rgba(0,0,0,.12)" stroke-width="2.2" />
                                <path d="M84,130 C86,190 80,240 74,290" stroke="rgba(255,255,255,.07)" stroke-width="3" />
                                <path d="M316,130 C314,190 320,240 326,290" stroke="rgba(255,255,255,.07)" stroke-width="3" />
                            </g>
                            <use href="#hb-ribs" />
                            <use href="#hb-hoodB" class="fabric" stroke="rgba(0,0,0,.4)" stroke-width="1.4" stroke-linejoin="round" />
                            <path d="M200,10 C201,50 199,100 200,143" fill="none" stroke="rgba(0,0,0,.24)" stroke-width="1.4" />
                            <path d="M150,70 C152,104 174,132 200,134" fill="none" stroke="rgba(0,0,0,.12)" stroke-width="3" stroke-linecap="round" />

                            <g pointer-events="none">
                                <use href="#hb-sil" fill="url(#hb-shade)" />
                                <use href="#hb-hoodB" fill="url(#hb-shade)" />
                            </g>
                        </g>

                        <!-- LOGOS -->
                        <template v-for="k in KEYS" :key="k">
                            <g
                                v-if="slots[k].src"
                                v-show="view === CFG[k].view"
                                class="logo"
                                :class="{ drag: dragKey === k }"
                                tabindex="0"
                                @pointerdown="onDown(k, $event)"
                                @pointermove="onMove(k, $event)"
                                @pointerup="onUp"
                                @pointercancel="onUp"
                                @keydown="onKey(k, $event)"
                                @click="onLogoClick(k, $event)"
                            >
                                <image
                                    :href="slots[k].src!"
                                    :x="boxes[k].x"
                                    :y="boxes[k].y"
                                    :width="boxes[k].w"
                                    :height="boxes[k].h"
                                    preserveAspectRatio="xMidYMid meet"
                                />
                                <g class="sel">
                                    <rect class="selA" :x="boxes[k].x" :y="boxes[k].y" :width="boxes[k].w" :height="boxes[k].h" />
                                    <rect class="selB" :x="boxes[k].x" :y="boxes[k].y" :width="boxes[k].w" :height="boxes[k].h" />
                                </g>
                            </g>
                        </template>
                    </svg>
                    <button class="download-btn" v-if="hasDesign" @click="downloadImage">تنزيل التصميم</button>
                </section>

                <!-- Controls -->
                <div class="panel">
                    <section class="card colors-swatches" aria-labelledby="hb-h-color">
                        <div class="swatches">
                            <button
                                v-for="c in COLORS"
                                :key="c.id"
                                type="button"
                                class="sw"
                                :aria-pressed="colorId === c.id"
                                @click="colorId = c.id"
                            >
                                <span class="chip" :style="{ background: c.hex }"></span>
                            </button>
                        </div>
                    </section>

                    <template v-for="k in KEYS" :key="k">
                        <article
                            v-if="view === CFG[k].view"
                            class="card"
                            :class="{ over: overKey === k }"
                            :data-active="view === CFG[k].view"
                            @dragover.prevent="overKey = k"
                            @dragleave="overKey = null"
                            @drop.prevent="onDrop(k, $event)"
                            @focusin="view = CFG[k].view"
                        >
                            <input
                                :ref="(el) => setInput(k, el)"
                                type="file"
                                accept="image/png,image/jpeg,image/webp,image/svg+xml"
                                hidden
                                @change="onFile(k, $event)"
                            />

                            <div class="field">
                                <span class="lbl">الموضع</span>
                                <div class="seg" role="group" :aria-label="`${CFG[k].title} الموضع`">
                                    <button
                                        v-for="(p, pk) in PRESETS[k]"
                                        :key="pk"
                                        type="button"
                                        :disabled="!slots[k].src"
                                        :aria-pressed="!!slots[k].src && slots[k].preset === pk"
                                        @click="choosePreset(k, pk)"
                                    >
                                        {{ p.label }}
                                    </button>
                                </div>
                            </div>

                            <div class="field stretch">
                                <label class="lbl" :for="`hb-size-${k}`">
                                    العرض <output>{{ slots[k].cm }} سم</output>
                                </label>
                                <input
                                    :id="`hb-size-${k}`"
                                    v-model.number="slots[k].cm"
                                    type="range"
                                    :min="CFG[k].min"
                                    :max="CFG[k].max"
                                    step="1"
                                    :disabled="!slots[k].src"
                                />
                            </div>

                            <p class="note" role="status">{{ notes[k] }}</p>
                        </article>
                    </template>
                </div>
            </div>
        </div>
    </div>
</template>

<script setup lang="ts">
import { computed, reactive, ref } from 'vue'
import oImg from '../assets/o.png'

type SlotKey = 'chest' | 'back'
type View = 'front' | 'back'

interface Preset {
    label: string
    cx: number
    cy: number
    cm: number
}

interface Slot {
    src: string | null
    name: string
    sample: boolean
    vector: boolean
    px: number
    py: number
    ar: number
    preset: string | null
    cx: number
    cy: number
    cm: number
}

interface SlotConfig {
    title: string
    min: number
    max: number
    maxH: number
    x: [number, number]
    y: [number, number]
    view: View
}

const COLORS = [
    { id: 'wine', name: 'Burgundy', hex: '#6B1F34' },
    { id: 'navy', name: 'Navy', hex: '#1B2A49' },
    { id: 'black', name: 'Black', hex: '#17181A' },
    { id: 'grey', name: 'Grey', hex: '#8D939B' },
    { id: 'sky', name: 'Sky Blue', hex: '#8EC5E8' },
]

const KEYS: SlotKey[] = ['chest', 'back']

// Positions are in hoodie drawing units. 3 units = 1 cm (the body is about 56 cm across).
const PRESETS: Record<SlotKey, Record<string, Preset>> = {
    chest: {
        center: { label: 'وسط', cx: 200, cy: 226, cm: 24 },
        left: { label: 'صدر أيمن', cx: 240, cy: 160, cm: 9 },
    },
    back: {
        center: { label: 'وسط الظهر', cx: 200, cy: 260, cm: 32 },
        upper: { label: 'أعلى الظهر', cx: 200, cy: 184, cm: 16 },
    },
}

const CFG: Record<SlotKey, SlotConfig> = {
    chest: { title: 'شعار الصدر', min: 6, max: 32, maxH: 150, x: [130, 270], y: [130, 268], view: 'front' },
    back: { title: 'شعار الظهر', min: 10, max: 40, maxH: 230, x: [130, 270], y: [150, 396], view: 'back' },
}

const enc = (svg: string) => 'data:image/svg+xml;charset=utf-8,' + encodeURIComponent(svg)

const SAMPLE_CHEST = enc(
    '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 120 120"><rect x="3" y="3" width="114" height="114" rx="14" fill="#14181F" fill-opacity=".88" stroke="#fff" stroke-width="3" stroke-dasharray="9 6"/><text x="60" y="56" text-anchor="middle" font-family="Arial, Helvetica, sans-serif" font-weight="700" font-size="22" fill="#fff">شعار</text><text x="60" y="84" text-anchor="middle" font-family="Arial, Helvetica, sans-serif" font-weight="700" font-size="22" fill="#fff">هنا</text></svg>',
)
const SAMPLE_BACK = enc(
    '<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 300 80"><rect x="3" y="3" width="294" height="74" rx="14" fill="#14181F" fill-opacity=".88" stroke="#fff" stroke-width="3" stroke-dasharray="9 6"/><text x="150" y="51" text-anchor="middle" font-family="Arial, Helvetica, sans-serif" font-weight="700" font-size="28" fill="#fff">الشعار هنا</text></svg>',
)

const colorId = ref('wine')
const view = ref<View>('front')
const overKey = ref<SlotKey | null>(null)
const dragKey = ref<SlotKey | null>(null)

const svgEl = ref<SVGSVGElement | null>(null)
const inputs: Record<SlotKey, HTMLInputElement | null> = { chest: null, back: null }

const notes = reactive<Record<SlotKey, string>>({ chest: '', back: '' })

const slots = reactive<Record<SlotKey, Slot>>({
    chest: { src: SAMPLE_CHEST, name: 'شعار تجريبي', sample: true, vector: true, px: 0, py: 0, ar: 1, preset: 'center', cx: 200, cy: 226, cm: 24 },
    back: { src: SAMPLE_BACK, name: 'شعار تجريبي', sample: true, vector: true, px: 0, py: 0, ar: 300 / 80, preset: 'center', cx: 200, cy: 260, cm: 32 },
})

const currentColor = computed(() => COLORS.find((c) => c.id === colorId.value) ?? COLORS[0])
const activeKey = computed(() => KEYS.find((k) => CFG[k].view === view.value) ?? 'chest')
const hasDesign = computed(() => {
    const s = slots[activeKey.value]
    return !!s.src && !s.sample
})

function box(k: SlotKey) {
    const s = slots[k]
    let w = s.cm * 3
    let h = w / s.ar
    const maxH = CFG[k].maxH
    if (h > maxH) {
        h = maxH
        w = h * s.ar
    }
    return { x: s.cx - w / 2, y: s.cy - h / 2, w, h }
}
const boxes = computed(() => ({ chest: box('chest'), back: box('back') }))

/* ---------- controls ---------- */
function setInput(k: SlotKey, el: unknown) {
    inputs[k] = el as HTMLInputElement | null
}

function choosePreset(k: SlotKey, key: string) {
    const p = PRESETS[k][key]
    const s = slots[k]
    s.cx = p.cx
    s.cy = p.cy
    s.cm = p.cm
    s.preset = key
    view.value = CFG[k].view
}

/* ---------- download ---------- */
async function downloadImage() {
    const svg = svgEl.value
    const k = activeKey.value
    if (!svg || !hasDesign.value) return

    try {
        // Serialize a copy of the visible SVG. Colors are inlined because the
        // standalone SVG image has no access to the page's CSS variables.
        const clone = svg.cloneNode(true) as SVGSVGElement
        clone.querySelectorAll('.sel').forEach((el) => el.remove())
        clone.removeAttribute('style')
        clone.setAttribute('width', '800')
        clone.setAttribute('height', '920')

        const style = document.createElementNS('http://www.w3.org/2000/svg', 'style')
        style.textContent = `.fabric{fill:${currentColor.value.hex}}`
        clone.prepend(style)

        const url = enc(new XMLSerializer().serializeToString(clone))
        const img = new Image()
        await new Promise<void>((resolve, reject) => {
            img.onload = () => resolve()
            img.onerror = () => reject(new Error('load'))
            img.src = url
        })

        const canvas = document.createElement('canvas')
        canvas.width = 800
        canvas.height = 1070
        const ctx = canvas.getContext('2d')
        if (!ctx) throw new Error('canvas')
        ctx.fillStyle = '#eef0f3'
        ctx.fillRect(0, 0, canvas.width, canvas.height)
        ctx.drawImage(img, 0, 0, 800, 920)

        const s = slots[k]
        const lines = [
            `الجهة: ${view.value === 'front' ? 'الواجهة' : 'الخلفية'}`,
            `الموقع: ${s.preset ? PRESETS[k][s.preset].label : 'موضع مخصص'}`,
            `حجم التصميم: ${s.cm}cm`,
        ]
        ctx.fillStyle = '#14181f'
        ctx.font = '600 28px system-ui, Arial, sans-serif'
        ctx.direction = 'rtl'
        ctx.textAlign = 'right'
        ctx.textBaseline = 'middle'
        lines.forEach((text, i) => ctx.fillText(text, 760, 950 + i * 44))

        const link = document.createElement('a')
        link.download = `${CFG[k].view}-hoodie-design.png`
        link.href = canvas.toDataURL('image/png')
        link.click()
        notes[k] = 'تمت عملية التحميل بنجاح.'
    } catch {
        notes[k] = 'تعذر تحميل الصورة. حاول مرة أخرى.'
    }
}

/* ---------- upload ---------- */
function onFile(k: SlotKey, e: Event) {
    const input = e.target as HTMLInputElement
    loadFile(k, input.files?.[0])
    input.value = ''
}

function onDrop(k: SlotKey, e: DragEvent) {
    overKey.value = null
    loadFile(k, e.dataTransfer?.files?.[0])
}

function loadFile(k: SlotKey, file?: File) {
    notes[k] = ''
    if (!file) return
    if (!/^image\/(png|jpeg|webp|svg\+xml)$/.test(file.type)) {
        notes[k] = 'استخدم ملف PNG أو JPG أو WebP أو SVG.'
        return
    }
    if (file.size > 8 * 1024 * 1024) {
        notes[k] = 'هذا الملف أكبر من 8 ميجابايت. قم بتصدير نسخة أصغر ثم حاول مرة أخرى.'
        return
    }
    const reader = new FileReader()
    reader.onerror = () => {
        notes[k] = 'تعذر قراءة الملف. حاول مرة أخرى.'
    }
    reader.onload = () => {
        const dataUrl = String(reader.result)
        const img = new Image()
        img.onload = () => {
            const vector = file.type === 'image/svg+xml'
            const nw = img.naturalWidth || 100
            const nh = img.naturalHeight || 100
            const s = slots[k]
            s.src = dataUrl
            s.name = file.name
            s.sample = false
            s.vector = vector
            s.px = vector ? 0 : nw
            s.py = vector ? 0 : nh
            s.ar = nw / nh
            view.value = CFG[k].view
        }
        img.onerror = () => {
            notes[k] = 'تعذر فتح هذه الصورة. حاول تصديرها مرة أخرى.'
        }
        img.src = dataUrl
    }
    reader.readAsDataURL(file)
}

function onLogoClick(k: SlotKey, e: MouseEvent) {
    if (slots[k].sample) {
        inputs[k]?.click()
        e.stopPropagation()
    }
}

/* ---------- drag and keys on the hoodie ---------- */
let drag: { k: SlotKey; dx: number; dy: number } | null = null

function toSvg(e: PointerEvent) {
    const svg = svgEl.value
    if (!svg) return { x: e.clientX, y: e.clientY }
    const pt = svg.createSVGPoint()
    pt.x = e.clientX
    pt.y = e.clientY
    const m = svg.getScreenCTM()
    return m ? pt.matrixTransform(m.inverse()) : pt
}

function clamp(v: number, a: number, b: number) {
    return Math.max(a, Math.min(b, v))
}

function moveTo(k: SlotKey, x: number, y: number) {
    const s = slots[k]
    const c = CFG[k]
    s.cx = clamp(x, c.x[0], c.x[1])
    s.cy = clamp(y, c.y[0], c.y[1])
    s.preset = null
}

function onDown(k: SlotKey, e: PointerEvent) {
    if (e.button > 0 || slots[k].sample) return
    ;(e.currentTarget as SVGGElement).setPointerCapture(e.pointerId)
    const p = toSvg(e)
    drag = { k, dx: slots[k].cx - p.x, dy: slots[k].cy - p.y }
    dragKey.value = k
    e.preventDefault()
}

function onMove(k: SlotKey, e: PointerEvent) {
    if (!drag || drag.k !== k) return
    const p = toSvg(e)
    moveTo(k, p.x + drag.dx, p.y + drag.dy)
}

function onUp() {
    drag = null
    dragKey.value = null
}

function onKey(k: SlotKey, e: KeyboardEvent) {
    const step = e.shiftKey ? 8 : 2
    let dx = 0
    let dy = 0
    if (e.key === 'ArrowLeft') dx = -step
    else if (e.key === 'ArrowRight') dx = step
    else if (e.key === 'ArrowUp') dy = -step
    else if (e.key === 'ArrowDown') dy = step
    else return
    e.preventDefault()
    moveTo(k, slots[k].cx + dx, slots[k].cy + dy)
}
</script>

<style scoped>
@property --hood {
    syntax: '<color>';
    inherits: true;
    initial-value: #6b1f34;
}

.hb {
    --bg: #eef0f3;
    --surface: #ffffff;
    --stage: #dfe4ea;
    --fg: #14181f;
    --muted: #566170;
    --line: #d1d8e0;
    --accent: #f2c230;
    --accent-fg: #14181f;
    --focus: #2b5fd9;
    --warn: #b3261e;
    --chk1: #e9edf1;
    --chk2: #c9d0d8;
    --font-body: system-ui, -apple-system, 'Segoe UI', Roboto, sans-serif;
    --font-mono: ui-monospace, 'SF Mono', Menlo, Consolas, monospace;

    background: var(--bg);
    color: var(--fg);
    font-family: var(--font-body);
    font-size: 15px;
    line-height: 1.45;
    height: 100vh;
    padding-inline: 16px;
    display: flex;
    flex-direction: column;
    gap: 12px;
    direction: rtl;
}
.hb *,
.hb *::before,
.hb *::after {
    box-sizing: border-box;
}
.hb > * {
    width: 100%;
    max-width: 1080px;
    margin-inline: auto;
}
.hb button,
.hb input {
    font-family: inherit;
}
.hb :focus-visible {
    outline: 3px solid var(--focus);
    outline-offset: 2px;
}

.top {
    display: grid;
    gap: 6px;
}
h1 {
    margin: 0;
    font-size: clamp(22px, 4.6vw, 30px);
    font-weight: 700;
    letter-spacing: -0.02em;
    text-wrap: balance;
}
.sub {
    margin: 0;
    color: var(--muted);
    max-width: 52ch;
}

.app {
    display: grid;
    gap: 20px;
    grid-template-columns: minmax(0, 1fr);
    flex: 1 1 auto;
    overflow: hidden;
}
@media (min-width: 860px) {
    .app {
        grid-template-columns: minmax(0, 1.1fr) minmax(320px, 0.9fr);
        align-items: start;
    }
}

.stage {
    background: var(--stage);
    border-radius: 20px;
    padding: 14px;
    display: grid;
    gap: 6px;
    min-width: 0;
    height: 100%;
    overflow: visible;
}
.stage-top {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 12px;
    flex-wrap: wrap;
}
.colorname {
    font-size: 15px;
    font-weight: 700;
}
.hoodie {
    display: block;
    width: 100%;
    height: auto;
    max-height: 44vh;
    margin: 0 auto;
    transition: --hood 0.35s ease;
}
.fabric {
    fill: var(--hood);
}
.logo {
    cursor: grab;
    touch-action: none;
    outline: none;
}
.logo.drag {
    cursor: grabbing;
}
.sel {
    display: none;
    fill: none;
}
.logo:hover .sel,
.logo:focus-visible .sel,
.logo.drag .sel {
    display: inline;
}
.selA {
    stroke: rgba(0, 0, 0, 0.5);
    stroke-width: 2.5;
}
.selB {
    stroke: #fff;
    stroke-width: 1.2;
    stroke-dasharray: 4 3;
}
.stage-hint {
    margin: 0;
    text-align: center;
    font-size: 12.5px;
    color: var(--muted);
}
.download-btn {
    font-size: 14px;
    font-weight: 600;
    padding: 10px 10px;
    border-radius: 9px;
    border: 1px solid var(--line);
    background: var(--accent);
    color: var(--fg);
    cursor: pointer;
    width: 100%;
}
.panel {
    display: grid;
    gap: 14px;
    min-width: 0;
    height: 100%;
    overflow: auto;
}
.card {
    background: var(--surface);
    border: 1px solid var(--line);
    border-radius: 14px;
    padding: 16px;
    display: grid;
    gap: 14px;
    min-width: 0;
    margin-bottom: 16px;
}
.card[data-active='true'] {
    border-color: var(--fg);
}
.card.over {
    outline: 2px dashed var(--fg);
    outline-offset: -7px;
}
.card-h {
    display: flex;
    justify-content: space-between;
    align-items: center;
    gap: 10px;
}
h2 {
    margin: 0;
    font-size: 15px;
    font-weight: 600;
}
.tag {
    font-family: var(--font-mono);
    font-size: 11px;
    text-transform: uppercase;
    letter-spacing: 0.08em;
    color: var(--muted);
}

.colors-swatches{
    padding: 5px;
}

.swatches {
    display: grid;
    grid-template-columns: repeat(5, minmax(0, 1fr));
    gap: 6px;
    align-items: center;
}
.sw {
    display: grid;
    justify-items: center;
    gap: 7px;
    background: none;
    border: 0;
    padding: 4px 0;
    font-size: 11px;
    color: var(--muted);
    cursor: pointer;
}
.chip {
    width: 28px;
    height: 28px;
    border-radius: 50%;
    box-shadow: inset 0 0 0 1px rgba(128, 128, 128, 0.4);
}
.sw[aria-pressed='true'] {
    color: var(--fg);
    font-weight: 600;
}
.sw[aria-pressed='true'] .chip {
    box-shadow:
        0 0 0 2px var(--surface),
        0 0 0 4px var(--fg);
}

.seg {
    display: inline-flex;
    border: 1px solid var(--line);
    border-radius: 10px;
    padding: 3px;
    gap: 2px;
    background: var(--surface);
    max-width: 100%;
}
.seg button {
    font-size: 13px;
    font-weight: 500;
    border: 0;
    background: transparent;
    color: var(--fg);
    padding: 7px 12px;
    border-radius: 7px;
    cursor: pointer;
}
.seg button[aria-pressed='true'] {
    background: var(--accent);
    color: var(--accent-fg);
}
.seg button:disabled {
    opacity: 0.4;
    cursor: not-allowed;
}

.file {
    display: grid;
    grid-template-columns: auto minmax(0, 1fr);
    gap: 12px;
    align-items: center;
}
.thumb {
    width: 54px;
    height: 54px;
    border-radius: 9px;
    border: 1px solid var(--line);
    overflow: hidden;
    display: grid;
    place-items: center;
    background: conic-gradient(var(--chk1) 25%, var(--chk2) 0 50%, var(--chk1) 0 75%, var(--chk2) 0) 0 0 / 12px 12px;
}
.thumb img {
    max-width: 100%;
    max-height: 100%;
    object-fit: contain;
}
.fileinfo {
    min-width: 0;
    display: grid;
    gap: 2px;
}
.fname {
    font-weight: 600;
    overflow: hidden;
    text-overflow: ellipsis;
    white-space: nowrap;
    background: none;
    border: none;
    padding: 0;
    text-align: start;
    cursor: pointer;
    color: inherit;
}
.meta {
    font-family: var(--font-mono);
    font-size: 11.5px;
    color: var(--muted);
}
.meta.warn {
    color: var(--warn);
}
.actions {
    grid-column: 1 / -1;
    display: flex;
    gap: 8px;
    flex-wrap: wrap;
}
.btn {
    font-size: 13.5px;
    font-weight: 600;
    padding: 9px 14px;
    border-radius: 9px;
    border: 1px solid var(--line);
    background: var(--surface);
    color: var(--fg);
    cursor: pointer;
}
.btn.primary {
    background: var(--accent);
    border-color: transparent;
    color: var(--accent-fg);
}
.btn:disabled {
    opacity: 0.45;
    cursor: not-allowed;
}

.field {
    display: grid;
    gap: 7px;
    justify-items: start;
}
.field.stretch {
    justify-items: stretch;
}
.lbl {
    font-size: 12.5px;
    font-weight: 600;
    color: var(--muted);
    display: flex;
    gap: 8px;
    align-items: baseline;
}
.lbl output {
    font-family: var(--font-mono);
    font-weight: 500;
    color: var(--fg);
}
input[type='range'] {
    width: 100%;
    accent-color: var(--fg);
    margin: 0;
}
.note {
    margin: 0;
    min-height: 1.2em;
    font-size: 12.5px;
    color: var(--warn);
}

@media (prefers-reduced-motion: reduce) {
    .hoodie {
        transition: none;
    }
}
</style>