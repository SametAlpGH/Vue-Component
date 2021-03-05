<template>
	<div v-bind:id="'BaseDiv_' + propsData.ID" class="base-holder">
		<div class="data-group-container">
			<div class="data-group-container">
                <div class="data-group-header clear-padding" v-bind:id="'data-group-header-' + propsData.ID">{{propsData.Header}}</div>
				<div class="data-group-table">
					<div class="data-group-row clear-padding" v-for="(currentDataArray, parentIndex) in displayerData" v-bind:key="parentIndex">
							<div class="data-group-cell" style="width: 50%;" v-for="(item, childIndex) in currentDataArray" v-bind:key="childIndex">
								<div class="data-group-cell-header" v-bind:id="'data-group-cell-header-' + propsData.ID + parentIndex + childIndex">{{item.Label}}</div>
								<div class="data-group-cell-value" v-bind:id="'data-group-cell-value-' + propsData.ID + parentIndex + childIndex">{{item.Value}}</div>
							</div>
					</div>
					<!-- <div class="isweb-loading-image-container hidden-spinner isweb-list-spinner">
						<div class="isweb-loading-image"></div>
					</div> -->
				</div>
			</div>
		</div>
        <!-- <div>{{displayerData}}</div> -->
	</div>
</template>

 <script>
 export default {
      props: ["propsData"],
      computed:{
          displayerData(){
              let sourceData = this.propsData.LabelAndValue;
              let chunkedArray = [];
              while(sourceData.length){
                  chunkedArray.push(sourceData.splice(0,2))
                  console.log(chunkedArray)
              }
              return chunkedArray;
          }

      }
};
 </script>

 <style scoped>
 .data-group-container .data-group-header {
    display: block;
    width: 100%;
    line-height: 36px;
    padding-left: 24px;
    background-color: #f8f8f8;
    color: #08335e;
    border-top: solid 1px #e5e5e5;
    border-bottom: solid 1px #e5e5e5;
    font-weight: bold;
    font-size: 12px;
}

.data-group-container .data-group-header.clear-padding {
    padding-left: 0;
}

.data-group-container .data-group-header.bg-color-white {
    background-color: #ffffff;
}

@media only screen and (max-width: 767px) {
    .data-group-container .data-group-header {
        padding-left: 13px;
    }
}

.data-group-container .data-group-table {
    display: block;
    padding-top: 5px;
}

@media only screen and (max-width: 767px) {
    .data-group-container .data-group-table {
        padding: 0 13px 20px 13px;
    }
}

.data-group-container .data-group-table .data-group-row {
    padding: 9px 24px;
    font-size: 14px;
}

.data-group-container .data-group-table .data-group-row.clear-padding {
    padding-left: 0;
    padding-right: 0;
}

@media only screen and (max-width: 767px) {
    .data-group-container .data-group-table .data-group-row {
        padding: 0;
    }
}

.data-group-container .data-group-table .data-group-row .data-group-cell {
    display: inline-block;
    vertical-align: top;
    padding-right: 10px;
}

@media only screen and (max-width: 767px) {
    .data-group-container .data-group-table .data-group-row .data-group-cell {
        display: block;
        width: 100% !important;
        padding-top: 14px;
        padding-right: 0;
    }
}

.data-group-container .data-group-table .data-group-row .data-group-cell .data-group-cell-header {
    display: block;
    min-height: 16px;
    color: #9b9b9b;
    font-weight: 400;
}

.data-group-container .data-group-table .data-group-row .data-group-cell .data-group-cell-value {
    display: block;
    padding-top: 4px;
    font-weight: bold;
    word-wrap: break-word;
    color:black
}

.data-group-container .data-group-table .data-group-row .data-group-cell .data-group-cell-value .datagroup-inline-tooltip {
    display: inline-block;
    width: 21px;
    height: 21px;
    margin-right: 10px;
    margin-left: -5px;
}

.data-group-container .data-group-header.clear-padding {
    padding-left: 0;
}
@media only screen and (max-width: 767px) {
    .data-group-container .data-group-table .data-group-row .data-group-cell .data-group-cell-value {
        font-weight: bold;
    }
}

@media only screen and (max-width: 767px) {
    .data-group-container .data-group-table .data-group-row .data-group-cell.data-group-empty-cell {
        display: none;
    }
}
 </style>