<script setup lang="ts">
/**
 * DesktopLayout Component
 * 
 * Provides the main shell for the Psy Labs OS interface.
 * Handles the background H1 graffiti, desktop icons grid, 
 * the main router view for windows, and the global navigation dock.
 */
import DesktopIcon from './DesktopIcon.vue'
import PsyDock from './PsyDock.vue'
</script>

<template>
  <div class="relative w-screen h-[100dvh] overflow-hidden bg-abstract text-white font-mono z-0">
    <!-- 
      Background H1 Graffiti 
      Static liquid effect with vintage noise texture.
      Positioned behind all interactive elements (z-[-1]).
    -->
    <div class="absolute inset-0 flex items-center justify-center pointer-events-none z-[-1] opacity-95 p-6 md:p-8">
      <div class="graffiti-wrapper -rotate-2">
        <!-- Layer 1: The Dark Stroke (Background) -->
        <h1 
          class="text-5xl md:text-7xl lg:text-8xl text-center text-liquid-graffiti-base text-liquid-graffiti-stroke py-4"
          style="font-family: var(--font-graffiti);"
          aria-hidden="true"
        >
          We build Web3<br>products<br>with <span class="passion-power">Passion</span>
        </h1>
        
        <!-- Layer 2: The Liquid Gradient Fill (Foreground) -->
        <h1 
          class="text-5xl md:text-7xl lg:text-8xl text-center text-liquid-graffiti-base text-liquid-graffiti-fill py-4"
          style="font-family: var(--font-graffiti);"
        >
          We build Web3<br>products<br>with <span class="passion-power">Passion</span>
        </h1>
      </div>
    </div>

    <!-- 
      Desktop Icons Grid
      Primary navigation for core OS applications.
    -->
    <div class="absolute top-0 left-0 p-4 flex flex-col flex-wrap gap-2 md:gap-4 h-[calc(100vh-8rem)] md:h-[calc(100vh-3rem)] z-10 items-start max-w-full overflow-visible">
      <DesktopIcon name="Who We Are" to="/who-we-are" iconName="Lentes Psy Labs Color.svg" />
      <DesktopIcon name="Achievements" to="/achievements" iconName="Bitcoin Psy Labs Color.png" />
      <DesktopIcon name="Portfolio" to="/portfolio" iconName="Laptop Psy Labs Color.svg" />
      <DesktopIcon name="Team" to="/team" iconName="Camisa PSY LABS Color.svg" />
      <DesktopIcon name="Contact" to="/contact" iconName="CPU COOKING COLOR.svg" />
    </div>

    <!-- 
      Application Window Manager
      Dynamic container for active windows via Vue Router.
    -->
    <router-view />

    <!-- 
      Psy-Aqua Dock
      Global navigation bar and system controls.
    -->
    <PsyDock />
  </div>
</template>
