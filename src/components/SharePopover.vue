<script setup lang="ts">
import ShareButton from '@/components/ShareButton.vue';
import { Popover, PopoverButton, PopoverPanel } from '@headlessui/vue';
import VisuallyHidden from '@/components/VisuallyHidden.vue';
</script>

<template>
  <div class="share-button">
    <Popover class="popover">
      <PopoverButton :as="ShareButton" />
      
      <PopoverPanel class="popover-panel">
        <span class="share-label">share</span>
        
        <nav>
          <ul class="social-media-icon-list">
            <li>
              <a href="#facebook">
                <VisuallyHidden>Facebook</VisuallyHidden>
                <img src="@/assets/icons/facebook.svg" alt="Facebook logo">
              </a>
            </li>
            <li>
              <a href="#x">
                <VisuallyHidden>X</VisuallyHidden>
                <img src="@/assets/icons/x.svg" alt="X logo">
              </a>
            </li>
            <li>
              <a href="#pinterest">
                <VisuallyHidden>Pinterest</VisuallyHidden>
                <img src="@/assets/icons/pinterest.svg" alt="Pinterest logo">
              </a>
            </li>
          </ul>
        </nav>
        
        <PopoverButton class="popover-button-close" :as="ShareButton" />
      </PopoverPanel>
    </Popover>
  </div>
</template>

<style scoped lang="scss">
@import '@/assets/styles/base/media-queries';

:deep() {
  .popover {
    @media #{$laptop-and-bigger} {
      position: relative;
    }
    
    .popover-panel {
      --background-color: var(--color-very-dark-grayish-blue);
      --border-radius: 10px;
      
      padding: 1rem 2rem;
      color: var(--color-grayish-blue);
      background-color: var(--background-color);
      border-radius: 0 0 var(--border-radius) var(--border-radius);
      position: absolute;
      left: 0;
      bottom: 0;
      right: 0;
      display: flex;
      align-items: center;
      gap: calc(17 / 16 * 1rem);
      
      @media #{$laptop-and-bigger} {
        --triangle-size: 1.5rem;
        --distance-to-popover-button: 1rem;
        
        padding: 1.125rem 2.25rem;
        border-radius: var(--border-radius);
        filter: drop-shadow(0 0.625rem 0.625rem var(--color-shadow-primary));
        bottom: revert;
        right: revert;
        top: calc((-1 * var(--distance-to-popover-button)) - (var(--triangle-size) / 2));
        left: 50%;
        transform: translate(-50%, -100%);
        
        &::after {
          content: '';
          border: calc(var(--triangle-size) / 2) solid transparent;
          border-top-color: var(--background-color);
          position: absolute;
          bottom: 0;
          left: 50%;
          transform: translate(-50%, calc(100% - 1px));
        }
      }
      
      .share-label {
        font-weight: 500;
        line-height: calc(20 / 13 * 1em);
        letter-spacing: calc(5 / 13 * 1em);
        text-transform: uppercase;
      }
      
      .social-media-icon-list {
        padding: 0;
        list-style: none;
        display: flex;
        align-items: center;
        gap: 1rem;
        
        a {
          text-decoration: none;
          
          img {
            min-width: 1.25rem;
          }
        }
      }
      
      .popover-button-close {
        color: white;
        background-color: var(--color-desaturated-dark-blue);
        flex-shrink: 0;
        
        @media #{$laptop-and-bigger} {
          display: none;
        }
        
        &:hover, &:focus-visible {
          color: var(--color-desaturated-dark-blue);
          background-color: var(--color-light-grayish-blue);
        }
      }
    }
  }
}
</style>
