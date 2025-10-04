        // Script executes after DOM is loaded
        document.addEventListener('DOMContentLoaded', function() {
            // Mod Features FAQ Toggle Function
            const featuresToggle = document.getElementById('mod-features-toggle');
            const featuresContent = document.getElementById('mod-features-content');
            const featuresIcon = featuresToggle.querySelector('.mod-app-premium-features-toggle svg');
            
            // Default open state
            featuresContent.classList.add('active');
            featuresIcon.style.transform = 'rotate(180deg)';
            
            featuresToggle.addEventListener('click', function() {
                featuresContent.classList.toggle('active');
                
                if (featuresContent.classList.contains('active')) {
                    featuresIcon.style.transform = 'rotate(180deg)';
                } else {
                    featuresIcon.style.transform = 'rotate(0deg)';
                }
            });
            
            // Button Click Effects
            const buttons = document.querySelectorAll('.mod-app-premium-download-button, .mod-app-premium-playstore-button');
            
            buttons.forEach(button => {
                button.addEventListener('mousedown', function() {
                    this.style.transform = 'translateY(2px)';
                });
                
                button.addEventListener('mouseup', function() {
                    if (this.classList.contains('mod-app-premium-download-button')) {
                        this.style.transform = 'translateY(-4px)';
                    } else {
                        this.style.transform = 'translateY(-3px)';
                    }
                });
                
                button.addEventListener('mouseleave', function() {
                    this.style.transform = 'translateY(0)';
                });
            });
            
            // Skeleton Loading Effect (Optional)
            function simulateLoading() {
                const infoBoxes = document.querySelectorAll('.mod-app-premium-box');
                
                // First hide all content and show skeleton
                infoBoxes.forEach(box => {
                    const content = box.querySelector('.mod-app-premium-content');
                    const icon = box.querySelector('.mod-app-premium-icon');
                    
                    // Save original content
                    const originalContentHTML = content.innerHTML;
                    
                    // Set skeleton content
                    icon.classList.add('mod-app-premium-skeleton', 'mod-app-premium-skeleton-icon');
                    
                    content.innerHTML = `
                        <b class="mod-app-premium-skeleton mod-app-premium-skeleton-text"></b>
                        <span class="mod-app-premium-skeleton mod-app-premium-skeleton-text" style="width: 80%"></span>
                    `;
                    
                    // Store original content for restoration
                    box.dataset.originalContent = originalContentHTML;
                });
                
                // Restore original content after 1.5 seconds
                setTimeout(() => {
                    infoBoxes.forEach((box, index) => {
                        setTimeout(() => {
                            const content = box.querySelector('.mod-app-premium-content');
                            const icon = box.querySelector('.mod-app-premium-icon');
                            
                            // Remove skeleton classes
                            icon.classList.remove('mod-app-premium-skeleton', 'mod-app-premium-skeleton-icon');
                            
                            // Restore original content
                            content.innerHTML = box.dataset.originalContent;
                            
                            // Animation effect
                            box.style.opacity = '0';
                            box.style.transform = 'translateY(10px)';
                            
                            setTimeout(() => {
                                box.style.transition = 'opacity 0.5s ease, transform 0.5s ease';
                                box.style.opacity = '1';
                                box.style.transform = 'translateY(0)';
                            }, 50);
                            
                        }, index * 100);
                    });
                }, 1500);
            }
            
            // Uncomment the line below to enable skeleton loading effect
            // simulateLoading();
        });
