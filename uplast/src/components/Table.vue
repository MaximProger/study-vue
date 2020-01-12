<template>
  <table class="table table-hover table-responsive-lg">
    <!-- table-responsive -->
    <thead class="table__head">
      <tr>
        <th scope="col">ID</th>
        <th scope="col">Name</th>
        <th scope="col">Email</th>
        <th scope="col">Message</th>
        <th scope="col">Action</th>
      </tr>
    </thead>
    <tbody class="table__body">
      <Loader v-if="loading" />
      <tr
        v-else
        v-bind:key="line.id"
        v-for="line in tableLine"
        class="table__line"
      >
        <th scope="row">{{ line.id }}</th>
        <td>{{ line.name }}</td>
        <td>{{ line.email }}</td>
        <td>{{ line.body }}</td>
        <td
          class="table__actions d-flex justify-content-center align-items-center"
        >
          <a
            href="#"
            class="table__del"
            title="Удалить"
            data-toggle="modal"
            data-target="#deleteLine"
            ><i class="fas fa-trash-alt"></i
          ></a>
        </td>
      </tr>
    </tbody>
  </table>
</template>

<script>
import Loader from '@/components/Loader'
export default {
  components: {
    Loader
  },
  data() {
    return {
      tableLine: [],
      loading: true
    }
  },
  mounted() {
    fetch('https://jsonplaceholder.typicode.com/comments?_limit=3')
      .then(response => response.json())
      .then(json => {
        this.tableLine = json
        this.loading = false
      })
  }
}
</script>

<style lang="scss" scoped>
table {
  margin-top: 20px;
}
.table__head {
  background-color: #0084db;
  color: white;
}

.table thead th {
  vertical-align: top;
}

.table__body {
  background-color: #fff;
}

.table__line {
  &:nth-child(even) {
    background-color: #f2f9fd;
  }

  small {
    color: #9fa1a3;
  }

  &--main {
    &:hover {
      background-color: #cce9ed;
    }
  }

  &--firstItem {
    display: none;

    &.show {
      display: table-row;
    }
  }

  &--secondItem {
    display: none;

    &.show {
      display: table-row;
    }
  }

  &--thirdItem {
    display: none;

    &.show {
      display: table-row;
    }
  }

  &--fourthItem {
    display: none;

    &.show {
      display: table-row;
    }
  }
}

.table__input {
  width: 100px;
  margin-right: 10px;
  text-align: right;
}

.table__actions {
  a {
    font-size: 1.5rem;
    color: #8c8c8c;
    margin-left: 10px;
    transition: color 0.2s linear;

    &:hover {
      color: #191919;
    }
  }
}

.table__cart {
  color: #8c8c8c;
  font-size: 1.3rem;
}

.table__show {
  font-size: 1.3rem;
}

.table__arrow {
  padding-top: 10px;
  color: #191919;
  font-size: 1.3rem;

  &--hide {
    display: none;
  }
}

.tooltip-inner {
  background-color: white;
  color: #000;
  border: 1px solid black;
}

.table__poduct__under {
  color: #676767;
  font-weight: normal;
}
</style>
