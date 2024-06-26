# svg-to-react

将SVG转换为React组件。

## 安装
```bash
deno install https://deno.land/x/svg2react/mod.ts
```
## 使用
```bash
cat xxxxx.svg | svg2react
```
会得到如下输出

```tsx
import { SVGProps } from "react"
export function DiqyeSvg(props: SVGProps<SVGSVGElement>) {
    return <svg viewBox="0 0 18 20" {...props}>
        <defs>
            <filter id="uuidxxx" color-interpolationFilters="auto">
                <feColorMatrix in="SourceGraphic" values="0 0 0 0 0.200000 0 0 0 0 0.200000 0 0 0 0 0.200000 0 0 0 1.000000 0"/>
            </filter>
        </defs>
        <g fill="none" fillRule="evenodd" strokeLinecap="round" strokeLinejoin="round" filter="url(#uuidxxx)" transform="translate(-16 -21)">
    
            <g stroke="#292D32" strokeWidth="1.382">
                <path d="M25 37.3c2.942 0 5.333-2.421 5.333-5.4v-4.5c0-2.979-2.39-5.4-5.333-5.4-2.942 0-5.333 2.421-5.333 5.4v4.5c0 2.979 2.39 5.4 5.333 5.4"/>
                <path d="M17 30.1v1.8c0 4.473 3.582 8.1 8 8.1s8-3.627 8-8.1v-1.8m-10.569-3.168a7.029 7.029 0 0 1 4.89 0m-4.072 2.7a6.083 6.083 0 0 1 3.262 0" opacity=".5"/>
            </g>
        </g>
    </svg>
    
}
```

## 主要解决的问题

- 去除冗余的标签和ID
- ID唯一化
- 转换为符合React SVG组件规范的的属性
- 格式化,Copy 友好
