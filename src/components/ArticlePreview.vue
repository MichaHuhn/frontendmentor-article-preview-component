<script setup lang="ts">
import SharePopover from '@/components/SharePopover.vue';
</script>

<template>
  <article>
    <div class="top-image-wrapper">
      <img src="@/assets/images/drawers.jpg" alt="">
    </div>
    
    <div class="content">
      <hgroup class="text-content">
        <h1>
          Shift the overall look and feel by adding these wonderful
          touches to furniture in your home
        </h1>
        <p>
          Ever been in a room and felt like something was missing? Perhaps
          it felt slightly bare and uninviting. I’ve got some simple tips
          to help you make any room feel complete.
        </p>
      </hgroup>
      
      <div class="share-section">
        <figure>
          <div class="profile-picture-wrapper">
            <img src="@/assets/images/avatar-michelle.jpg" alt="Profile picture of Michelle Appleton" class="profile-picture">
          </div>
          <figcaption>
            <p class="name">Michelle Appleton</p>
            <p class="date">28 Jun 2020</p>
          </figcaption>
        </figure>
        
        <SharePopover class="share-button" />
      </div>
    </div>
  </article>
</template>

<style scoped lang="scss">
@import '@/assets/styles/base/media-queries';

article {
  --border-radius: 10px;
  --padding-inline: 2rem;
  
  max-width: 25rem;
  margin-inline: auto;
  background-color: white;
  border-radius: var(--border-radius);
  box-shadow: 0 2.5rem 2.5rem -0.625rem var(--color-shadow-primary);
  
  @media #{$laptop-and-bigger} {
    --padding-inline: 2.5rem;
    
    max-width: calc(730 / 16 * 1rem);
    display: flex;
  }
  
  .top-image-wrapper {
    height: 12.5rem;
    
    @media #{$laptop-and-bigger} {
      min-width: calc(285 / 16 * 1rem);
      height: revert;
    }
    
    img {
      width: 100%;
      height: 100%;
      object-fit: cover;
      object-position: left;
      border-radius: var(--border-radius) var(--border-radius) 0 0;
      
      @media #{$laptop-and-bigger} {
        border-radius: var(--border-radius) 0 0 var(--border-radius);
      }
    }
  }
  
  .text-content {
    padding-block-start: 2.25rem;
    padding-inline: var(--padding-inline);
    
    @media #{$laptop-and-bigger} {
      padding-block-start: 2rem;
    }
    
    h1 {
      color: var(--color-very-dark-grayish-blue);
      font-size: 1rem;
      font-weight: 700;
      line-height: calc(24 / 16 * 1em);
      letter-spacing: calc(0.2 / 16 * 1em);
      
      @media #{$laptop-and-bigger} {
        font-size: 1.25rem;
        line-height: calc(28 / 20 * 1em);
        letter-spacing: calc(0.25 / 16 * 1em);
      }
    }
    
    p {
      margin-block-start: 0.75rem;
      color: var(--color-desaturated-dark-blue);
      font-weight: 500;
      line-height: calc(20 / 13 * 1em);
      letter-spacing: calc(0.12 / 16 * 1em);
    }
  }
  
  .share-section {
    padding: 1.5rem var(--padding-inline) 1.25rem;
    position: relative;
    display: flex;
    align-items: center;
    gap: 1rem;
    
    @media #{$laptop-and-bigger} {
      padding: 1.25rem 2.5rem 2rem;
    }
    
    figure {
      display: flex;
      align-items: center;
      gap: 1rem;
      
      .profile-picture-wrapper {
        flex-shrink: 0;
        
        .profile-picture {
          width: 2.5rem;
          border-radius: 100vmax;
        }
      }
      
      .name {
        color: var(--color-very-dark-grayish-blue);
        font-weight: 700;
        line-height: calc(20 / 13 * 1em);
        letter-spacing: calc(0.12 / 13 * 1em);
      }
      
      .date {
        color: var(--color-grayish-blue);
        font-weight: 500;
        line-height: calc(20 / 13 * 1em);
        letter-spacing: calc(0.12 / 13 * 1em);
      }
    }
    
    .share-button {
      margin-inline-start: auto;
    }
  }
}
</style>
