<template>
    <div class="categoryMenu">
        <a class="categoryMenu__hero-link" href="#">
            <CategoriesIcon/> Shop all categories
        </a>

        <ul class="categoryMenu__list">
            <li class="categoryMenu__list-item">
                <a href="#" class="categoryMenu__link"><MyCatalogIcon/> My Catalog</a>
            </li>
            <li class="categoryMenu__list-item">
                <a href="#" class="categoryMenu__link"><MyListIcon/> My List</a>
            </li>
            <li class="categoryMenu__list-item">
                <a href="#" class="categoryMenu__link"><LiveHelpIcon/> Live Help</a>
            </li>
            <li class="categoryMenu__list-item">
                <a href="#" class="categoryMenu__link"><PIMIcon/> PIM</a>
            </li>
            <li class="categoryMenu__list-item">
                <a href="#" class="categoryMenu__link"><AccountIcon/> Account</a>
            </li>
            <li class="categoryMenu__list-item">
                <a href="#" class="categoryMenu__link"><BranchLocationsIcon/> Branch Locations</a>
            </li>
        </ul>
    </div>
</template>

<script>
// Icons
import CategoriesIcon from '../../assets/icons/ic_categories.svg';
import MyCatalogIcon from '../../assets/icons/ic_playlist_add_check.svg';
import MyListIcon from '../../assets/icons/ic_list.svg';
import LiveHelpIcon from '../../assets/icons/ic_chat.svg';
import PIMIcon from '../../assets/icons/ic_check_circle.svg';
import AccountIcon from '../../assets/icons/ic_person.svg';
import BranchLocationsIcon from '../../assets/icons/ic_place.svg';

export default {
  components: {
    CategoriesIcon,
    MyCatalogIcon,
    LiveHelpIcon,
    MyListIcon,
    PIMIcon,
    AccountIcon,
    BranchLocationsIcon,
  },

};
</script>

<style lang="scss">
@import '@/styles/_variables.scss';


.categoryMenu {
    box-sizing: border-box;

    @media (max-width: $tablet) {
        margin: 0 15px;
    }

    &__hero-link {
        font-weight: 700;
        display: flex;
        width: 100%;
        box-sizing: border-box;
        justify-content: center;
        align-items: center;
        text-decoration: none;
        padding: 10px 0;
        transition: all 0.3s;
        cursor: pointer;
        border-bottom: 2px solid $gray;
        font-size: 120%;
        position: relative;
        
        &:after {
            content: url('../../assets/icons/ic_arrow_forward.png');
            position: absolute;
            top: 50%;
            right: 20px;
            transform: translate(0, -50%);
            transition: all 0.3s;
            display: none;
        }

        &:active,
        &:visited {
            color: #000;
        }

        svg {
            fill: #000;
            height: 35px;
            width: 35px;
            transition: all 0.3s;
            margin-right: 10px;
        }  
        &:hover {
            svg {
                fill: $plattGreen;
            }  
            &:after {
                transform: translate(5px, -50%);
            }
        }

        @media (max-width: $tablet) {
            border-bottom: 1px solid $gray; 
            justify-content: flex-start;
            padding: 30px 20px;
            
            &:after {
                display: block;
            }
        }
    }

    &__list {
        list-style-type: none;
        margin: 0;
        padding: 0;
        display: flex;
        flex-wrap: wrap;
        box-sizing: border-box;
        &-item {
            width: calc(100% / 3);
            border-bottom: 2px solid $gray; 
            box-sizing: border-box;
            &:nth-of-type(3n - 1) {
                border-right: 2px solid $gray; 
                border-left: 2px solid $gray; 
            }
        }
        
        @media (max-width: $tablet) {
            &-item {
                width: 100%;
                border-bottom: 1px solid $gray; 
                box-sizing: border-box;
                &:nth-of-type(3n - 1) {
                    border-left: 0;
                    border-right: 0;
                }
                &:last-of-type {
                    border: 0;
                }
            }
        }
    }

    &__link {
        display: flex;
        box-sizing: border-box;
        width: 100%;
        justify-content: center;
        align-items: center;
        text-decoration: none;
        padding: 10px 20px;
        transition: all 0.3s;
        cursor: pointer;
        position: relative;

        &:after {
            content: url('../../assets/icons/ic_arrow_forward.png');
            position: absolute;
            top: 50%;
            right: 20px;
            transform: translate(0, -50%);
            transition: all 0.3s;
            display: none;
        }

        &:active,
        &:visited {
            color: #000;
        }
        svg {
            fill: #000;
            height: 30px;
            width: 30px;
            transition: all 0.3s;
            margin-right: 10px;
        }  
         &:hover {
            svg {
                fill: $plattGreen;
            }
            &:after {
                transform: translate(5px, -50%);
            }  
        }

        @media (max-width: $tablet) {
            justify-content: flex-start;

            &:after {
                display: block;
            }
        }
    }            
}

</style>
